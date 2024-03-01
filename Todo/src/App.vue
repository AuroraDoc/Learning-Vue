<template>
  <div class="container">
    <addTodos @submitTodoItem="addTodoItem"/>
    <todoList :todoItemList="todoItemList" @removedItem="removedItem"/>
  </div>
</template>

<script setup>
import addTodos from './components/addTodos.vue'
import todoList from './components/todoList.vue';

import { ref } from 'vue'

const todoItemList = ref([

])

const addTodoItem = (todoItemDesc) => {
  return todoItemList.value.push(todoItemDesc)//remember to do the lists value when trying to push
}

const removedItem = (index) => {
  todoItemList.value.splice(index, 1)
}

</script>