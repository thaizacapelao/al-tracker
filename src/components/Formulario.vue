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
        <section>
          <strong>00:00:00</strong>
        </section>
        <button class="button">
          <span class="icon">
            <i class="fas fa-play"></i>
          </span>
          <span>play</span>
        </button>
        <button class="button">
          <span class="icon">
            <i class="fas fa-stop"></i>
          </span>
          <span>stop</span>
        </button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Formulario',
});
</script>

<style>
.formulario {
  background-color: rgb(255, 255, 255);
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.5);
}

.formulario input {
  background-color: rgb(255, 255, 255);
  border-color: rgb(221, 220, 220);
}

.formulario input::placeholder {
  color: rgb(172, 171, 171);
}

.formulario button {
  background-color: rgb(255, 255, 255);
  border-color: rgb(221, 220, 220);
  color: rgb(105, 105, 105);
}

.formulario button:hover {
  background-color: rgb(214, 214, 214);
  transition: 0.9s;
}

.formulario strong {
  color: rgb(105, 105, 105);
}







</style>
