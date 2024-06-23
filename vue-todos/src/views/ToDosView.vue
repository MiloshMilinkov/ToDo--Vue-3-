<script setup>
import ToDoCreator from '@/components/ToDoCreator.vue';
import ToDoItem from '../components/ToDoItem.vue';
import { Icon } from '@iconify/vue';
import {uid} from "uid";
import {  ref } from 'vue';

const toDoList = ref([]);

const createToDo = (todo) =>{
  toDoList.value.push({
    id: uid(),
    todo: todo,
    isCompleted: null,
    isEditing: null,
  });
}
</script>

<template>
  <main>
    <h1>Create Todo</h1>
    <ToDoCreator @create-todo="createToDo" />
    <ul class="todo-list" v-if="toDoList.length > 0">
      <ToDoItem v-for="todo in toDoList" :todo="todo" />
    </ul>
    <p class="todos-msg" v-else>
      <Icon icon="noto-v1:sad-but-relieved-face"  width="22"></Icon>
      <span> You have no todo's, why not make one?</span>
    </p>
  </main>
</template>

<style lang="scss" scoped>
main{
  display: flex;
  flex-direction: column;
  max-width: 500px;
  width: 100%;
  margin: 0 auto;
  padding: 40px 16px;

  h1{
  margin-bottom: 16px;
  text-align: center;
  }

  .todo-list {
    display: flex;
    flex-direction: column;
    list-style: none;
    margin-top: 24px;
    gap: 20px;
  }

  .todos-msg {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    margin-top: 24px;
  }
}

</style>
