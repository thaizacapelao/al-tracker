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
        <Temporizador/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Temporizador from './Temporizador.vue'

export default defineComponent({
  name: "Formulario",
  components: {
    Temporizador
  },
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
