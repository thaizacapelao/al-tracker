<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral/>
    </div>
    <div class="column is-three-quarter">
      <Formulario/>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import Formulario from './components/Formulario.vue';

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    Formulario
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
