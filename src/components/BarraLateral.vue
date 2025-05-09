<template>
  <header>
    <h1>
      <img src="../assets/logo.png" alt="logo do al tracker" />
    </h1>
    <div
      class="tooltip-container"
      @mouseenter="tooltipVisivel = true"
      @mouseleave="tooltipVisivel = false"
    >
      <button class="button" @click="alterarTema">
        {{ textoBotao }}
      </button>
      <div v-if="tooltipVisivel" class="tooltip">Alterar tema da página</div>
    </div>
  </header>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "BarraLateral",
  emits: ["aoAlterarTema"],
  data() {
    return {
      modoEscuroAtivo: false,
      tooltipVisivel: false,
    };
  },
  computed: {
    textoBotao(): string {
      return this.modoEscuroAtivo ? "🌙" : "🔆";
    },
  },
  methods: {
    alterarTema() {
      this.modoEscuroAtivo = !this.modoEscuroAtivo;
      this.$emit("aoAlterarTema", this.modoEscuroAtivo);
    },
  },
});
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
  cursor: pointer;
}

button:hover {
  background: var(--bg-button-alterando-tema-hover);
}

.tooltip-container {
  position: relative;
  display: inline-block;
}

.tooltip {
  position: absolute;
  bottom: 40%;
  left: 224%;
  transform: translateX(-50%);
  background-color: #ffffff;
  color: rgba(49, 49, 49, 0.63);
  padding: 6px 10px;
  border-radius: 4px;
  white-space: nowrap;
  font-size: 14px;
  z-index: 1000;
  opacity: 0.9;
  transition: opacity 0.2s ease-in-out;
  box-shadow: 0px 0px 30px rgba(0, 0, 0, 0.5);
  border: 1px solid rgba(150, 150, 150, 0.5);
}

.tooltip::after {
  content: "";
  position: absolute;
  top: 50%;
  left: 0;
  transform: translate(-100%, -50%);
  border-width: 6px;
  border-style: solid;
  border-color: transparent #ffffff transparent transparent;
  
}


</style>
