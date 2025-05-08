<template>
    <header>
        <h1>
            <img src="../assets/logo.png" alt="logo do al tracker">
        </h1>
        <button class="button" @click="alterarTema">
          {{ textoBotao }}
        </button>
    </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
    name: 'BarraLateral',
    emits: ['aoAlterarTema'],
    data() {
      return {
        modoEscuroAtivo: false
      }
    },
    computed: {
      textoBotao() {
        if(this.modoEscuroAtivo) {
        return '🌙'
      }
      return '🔆'
    }
  },
    methods: {
      alterarTema() {
        this.modoEscuroAtivo = !this.modoEscuroAtivo;
        this.$emit('aoAlterarTema', this.modoEscuroAtivo);
      }
    }
})
</script>

<style scoped>
header {
  padding: 1rem;
  background: var(--bg-barra-lateral);
  width: 100%;
  height: 100vh;
  box-shadow: 0px 0px 50px rgba(129, 129, 129, 0.842);
  text-align: center;
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

button {
  background: var(--bg-button);
  color: #fff;
  border: var(--border-button);
  padding: 17px 20px;
  border-radius: 50%;
  margin-top: 2rem;
  box-shadow: var(--box-shadow-button);
}

button:hover {
  background: var(--bg-button-alterando-tema-hover);
}


</style>