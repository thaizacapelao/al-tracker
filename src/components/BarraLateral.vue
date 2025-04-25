<template>
    <header>
        <h1>
            <img src="../assets/logo.png" alt="logo do al tracker">
        </h1>
    </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
    name: 'BarraLateral'
})
</script>

<style scoped>
header {
  padding: 1rem;
  background: #705043e3;
  width: 100%;

  height: 100vh;
  box-shadow: 0px 0px 50px rgba(129, 129, 129, 0.842);
  z-index: 1;
}
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}

img {
  border-radius: 15%;
  box-shadow: 0px 0px 30px rgba(0, 0, 0, 0.5);
}

</style>