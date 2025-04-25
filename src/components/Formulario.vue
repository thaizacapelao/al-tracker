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
          v-model="descricao"
        />
      </div>
      <div class="column">
        <Temporizador @aoFinalizarTemporizador="finalizarTarefa"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Temporizador from './Temporizador.vue'

export default defineComponent({
  name: "Formulario",
  emits:['aoSalvarTarefa'],
  components: {
    Temporizador,
  },
  data () {
    return {
      descricao: ''
    }
  },
  methods: {
    finalizarTarefa(tempoDecorrido: number) : void {
      this.$emit('aoSalvarTarefa', {
        duracaoEmSegundos: tempoDecorrido,
        descricao: this.descricao
      })
      this.descricao = ''
    }
  }
});
</script>

<style>

.formulario {
  margin: 2rem 2rem 0 2rem;
  box-shadow: var(--bg-formulario-shadow);
  color: var(--texto-primario);
  background-color: var(--bg-formulario);
}

.formulario input {
  background-color: rgb(255, 255, 255);
  border-color: rgb(221, 220, 220);
  color: var(--texto-formulario);
}

.formulario input::placeholder {
  color: rgb(172, 171, 171);
}

.formulario button {
  background-color: rgb(255, 255, 255);
  border-color: rgb(221, 220, 220);
  color: rgba(92, 91, 91, 0.63);
}

.formulario button:hover {
  background-color: rgb(214, 214, 214);
  transition: background-color 0.7s ease-in-out;
}

</style>
