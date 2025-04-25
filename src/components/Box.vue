<template>
    <div class="box has-text-weight-bold">
        <slot></slot>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'Box',
    props: {
        titulo: {
            type: String,
            required: true  
        }
    }
})
</script>

<style scoped>
.box {
    background-color: var(--bg-box);
    border-color: rgb(221, 220, 220);
    margin: 1rem 2rem 0 2rem;
    color: var(--bg-box-color);
    box-shadow: var(--bg-box-shadow);
}


</style>