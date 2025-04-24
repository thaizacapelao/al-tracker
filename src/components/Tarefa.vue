<template>
    <div class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-8">
                {{ tarefa.descricao }}
            </div>
            <div class="column">
                <strong class="descricao"><Cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos" /></strong>
            </div>
        </div>
    </div>
</template>

<script lang="ts">

import { defineComponent, PropType } from 'vue';
import Cronometro from './Cronometro.vue'
import ITarefa from '../interfaces/ITarefa';

export default defineComponent({
    name: 'Tarefa',
    components: { 
        Cronometro 
    },
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
})
</script>

<style scoped>
.box {
    background-color: #f8f3dc;
    border-color: rgb(221, 220, 220);
    margin-right: 2rem;
    color: rgb(105, 105, 105);
    box-shadow: 0px 0px 10px rgba(129, 129, 129, 0.5);
}

</style>