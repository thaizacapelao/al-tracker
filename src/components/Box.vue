<template>
    <div class="box has-text-weight-bold" :style="estilos">
        <slot></slot>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'Box',
    data() {
        return {
            estilos: {
                backgroundColor: 'var(--bg-box)',
                borderColor: 'var(--bg-box-border)',
                color: 'var(--bg-box-color)',
                boxShadow: 'var(--bg-box-shadow)',
                margin: '1rem 2rem 0 2rem',
            }
        }
    },
    props: {
        titulo: {
            type: String,
            required: true  
        }
    }
})
</script>