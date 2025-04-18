<template>
  <div class="box formulario">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulário para criação de uma nova tarefa"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa você deseja iniciar?"
        />
      </div>
      <div class="column">
        <div
          class="is-flex is-align-items-center is-justify-content-space-between"
        >
          <section>
            <strong>{{ tempoDecorrido }}</strong>
          </section>
          <button class="button" @click="iniciar">
            <span class="icon">
              <i class="fas fa-play"></i>
            </span>
            <span>play</span>
          </button>
          <button class="button" @click="finalizar">
            <span class="icon">
              <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Formulario",
  data () {
    return {
      tempoEmSegundos: 0,
      cronometro: 0
    }
  },
  computed: {
    tempoDecorrido () : string {
      return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11,8)
    }
  },
  methods: {
    iniciar() {
     this.cronometro = setInterval(() => {
        this.tempoEmSegundos += 1
      }, 1000)
      console.log('Iniciando')
    },
    finalizar() {
      clearInterval(this.cronometro)
    }
  }
});
</script>

<style>
.formulario {
  background-color: rgb(255, 255, 255);
  box-shadow: 0px 0px 10px rgba(129, 129, 129, 0.5);
}

.formulario input {
  background-color: rgb(255, 255, 255);
  border-color: rgb(221, 220, 220);
  color: rgb(105, 105, 105);
}

.formulario input::placeholder {
  color: rgb(172, 171, 171);
}

.formulario button {
  background-color: rgb(255, 255, 255);
  border-color: rgb(221, 220, 220);
  color: rgb(92, 91, 91);
}

.formulario button:hover {
  background-color: rgb(214, 214, 214);
  transition: background-color 0.7s ease-in-out;
}

.formulario strong {
  color: rgb(105, 105, 105);
}
</style>
