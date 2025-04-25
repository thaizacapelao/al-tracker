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
        return 'Desativar modo escuro'
      }
      return 'Ativar modo escuro'
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
  background: #816155e3;
  width: 100%;
  height: 100vh;
  box-shadow: 0px 0px 50px rgba(129, 129, 129, 0.842);
  z-index: 1;
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
  background-color: #b19f98e3;
  color: #fff;
  padding: 10px 20px;
  border-radius: 5px;
}

</style>