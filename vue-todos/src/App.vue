<script setup>
import {  RouterView } from 'vue-router'
import ToDoHeader from './components/ToDoHeader.vue';
</script>

<template>
  <ToDoHeader/>
  <RouterView/>
</template>


<!-- Global style sheet, for the sake of base learning i will store this in APP.vue, better pracitce would be in a new css file in /assets -->
<style lang="scss">

@import url("https://fonts.googleapis.com/css2?family=Rubik:wght@300;400;500;700&display=swap");

* {
  font-family: "Rubik", sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {
  max-width: 1100px;
  margin: 0 auto;
}
</style>