<template>
  <main class="columns is-gapless is-multiline" :class="{'modo-escuro': modoEscuroAtivo}">
    <div class="column is-one-quarter">
      <BarraLateral @aoAlterarTema="alterarTema"/>
    </div>
    <div class="column is-three-quarter conteudo">
      <Formulario @aoSalvarTarefa="salvarTarefa"/>
      <div class="lista">
        <Tarefa v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa"/>
        <Box v-if="listaEstaVazia" titulo="Lista vazia">
          Você não esta muito produtivo hoje :(
        </Box>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import Formulario from './components/Formulario.vue';
import Tarefa from './components/Tarefa.vue';
import ITarefa from './interfaces/ITarefa';
import Box from './components/Box.vue';

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    Formulario,
    Tarefa,
    Box
  }, 
  data() {
    return {
        tarefas: [] as ITarefa[],
        modoEscuroAtivo: false
    }
  },
  computed: {
    listaEstaVazia(): boolean {
      return this.tarefas.length === 0;
    }
  },
  methods: {
    salvarTarefa(tarefa: ITarefa) {
      this.tarefas.push(tarefa);
    },
    alterarTema(modoEscuroAtivo: boolean) {
      this.modoEscuroAtivo = modoEscuroAtivo;
    }
  },
});
</script>

<style>
main {
  --bg-primario: #f5f5f5;
  --texto-primario: #afafaf;
  --texto-formulario: #afafaf;
  --bg-formulario-shadow: 0px 0px 10px rgba(129, 129, 129, 0.5);
  --bg-barra-lateral: #816155e3;
  --bg-box: #f8f3dc;
  --bg-box-color: rgb(105, 105, 105);
  --bg-box-shadow: 0px 0px 10px rgba(129, 129, 129, 0.5);
  --bg-button-alterando-tema: #a0bfd6;
  --bg-button-alterando-tema-hover: linear-gradient(to bottom, #7991a3 5%, #684721 100%);
  --box-shadow-button: 0px 2px 0px 0px #c38050;
  --border-button: 2px solid #634a41e3;
  --bg-button: linear-gradient(to bottom, #8ca8bd 5%, #7e5629 100%);
}

main.modo-escuro {
  --bg-primario: #343435;
  --texto-primario: #f5f3f3;
  --texto-formulario: #afaeae;
  --bg-formulario: #9e9e9e;
  --bg-formulario-shadow: 0px 0px 10px rgba(34, 34, 34, 0.5);
  --bg-barra-lateral: #382a25e3;
  --bg-box: #969077;
  --bg-box-color:rgb(255, 255, 255);
  --bg-box-shadow: 0px 0px 10px rgba(34, 34, 34, 0.5);
  --bg-button-alterando-tema: #212123e3;
  --bg-button-alterando-tema-hover: linear-gradient(to bottom, #3c3c3fe3 5%, #3c3c5ce3 100%);
  --box-shadow-button: 0px 2px 0px 0px #816451e3;
  --border-button: 2px solid #2f231be3;
  --bg-button: linear-gradient(to bottom, #2f2f31e3 5%, #383855e3 100%);
}

.lista {
  padding: 1.25rem;
}

strong {
  color: rgb(105, 105, 105) !important;
}

.conteudo {
  background-color: var(--bg-primario);
}

</style>
