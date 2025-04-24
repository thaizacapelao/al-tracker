<template>
    <div class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-8">
                Descrição da tarefa
            </div>
            <div class="column">
                <Cronometro :tempoEmSegundos="15" class="descricao" />
            </div>
        </div>
    </div>
</template>

<script lang="ts">

import { defineComponent } from 'vue';
import Cronometro from './Cronometro.vue'

export default defineComponent({
    name: 'Tarefa',
    components: { Cronometro }
})
</script>

<style scoped>
.box {
    background-color: #FAF0CA;
    border-color: rgb(221, 220, 220);
    margin-right: 2rem;

    color: rgb(105, 105, 105);
    box-shadow: 0px 0px 10px rgba(129, 129, 129, 0.5);
}

.descricao {
    color: rgb(105, 105, 105);
}
</style>