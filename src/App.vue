<template>
  <main class="columns is-gapless is-multiline ">
    <div class="column is-one-quarter">
      <BarraLateral/>
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
        tarefas: [] as ITarefa[]
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
    }
  },

});
</script>

<style>
main {
  --bg-primario: #f5f5f5;
  --texto-primario: #afafaf;
}

main.modo-escuro {
  --bg-primario: #343435;
  --texto-primario: #b1b1b1;
  --bg-formulario: #303031;
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
