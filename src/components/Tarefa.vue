<template>
    <Box :titulo="tarefa.descricao || 'Tarefa sem descrição'">
        <div class="columns">
            <div class="column is-8">
                {{ tarefa.descricao || 'Tarefa sem descrição' }}
            </div>
            <div class="column">
                <strong class="descricao"><Cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos" /></strong>
            </div>
        </div>
    </Box>
</template>

<script lang="ts">

import { defineComponent, PropType } from 'vue';
import Cronometro from './Cronometro.vue'
import ITarefa from '../interfaces/ITarefa';
import Box from './Box.vue';

export default defineComponent({
    name: 'Tarefa',
    components: { 
        Cronometro,
        Box
    },
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
})
</script>
