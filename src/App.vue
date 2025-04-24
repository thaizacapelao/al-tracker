<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral/>
    </div>
    <div class="column is-three-quarter">
      <Formulario/>
      <div class="lista">
        <Tarefa/>
        <Tarefa/>
        <Tarefa/>
        <Tarefa/>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import Formulario from './components/Formulario.vue';
import Tarefa from './components/Tarefa.vue';

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    Formulario,
    Tarefa
  }
});
</script>

<style>
html, body {
  background-color: white !important;
  height: 100%;
  margin: 0;
  padding: 0;
}

#app {
  height: 100%;
  background-color: white;
}
</style>
