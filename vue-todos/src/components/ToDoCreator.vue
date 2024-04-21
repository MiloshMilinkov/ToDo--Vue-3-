<script setup>
import { reactive, ref } from 'vue';

const todoState = reactive({
    todo:"Please enter a value"
});
</script>

<template>
    <div class="input-wrap">
        <input type="text" v-model="todoState.todo"/>
        <button>Create</button>
    </div>
</template>

<style lang="scss" scoped>
.input-wrap{
    display: flex;
    transition: 250ms ease;
    border: 2px solid #41b080;
    &:focus-within{
        box-shadow: 0 -4px 6px -1px rgb(0 0 0/0.1);
    }
    input{
        width: 100%;
        padding: 8px 6px;
        border: none;
        &:focus{
            outline: none;
        }
    }
    button{
        padding: 8px 16px;
        border: none;
    }
}
</style>