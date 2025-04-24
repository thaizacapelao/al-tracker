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
    background-color: #f8f3dc;
    border-color: rgb(221, 220, 220);
    margin-right: 2rem;
    color: rgb(105, 105, 105);
    box-shadow: 0px 0px 10px rgba(129, 129, 129, 0.5);
}

</style>