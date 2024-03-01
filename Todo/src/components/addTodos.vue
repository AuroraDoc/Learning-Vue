<template>
   
   <form @submit.prevent="submitTodoItem">
        <label for="inputTodo">Enter A Todo Item:</label>
        <br>
        <input type="text" v-model="todoItem" placeholder="Todo"> <button>+</button>
    </form>

</template>

<script setup>
import { ref } from 'vue'

const todoItem = ref('')// this is where I define what the v-model is
const emit = defineEmits(['submitTodoItem'])

const submitTodoItem = () => {
    if(todoItem.value == '') {
        alert('Please Fill a Todo Item')
    }

    let todoItemDesc = todoItem.value
    emit('submitTodoItem', todoItemDesc)

    todoItem.value = ''
}
</script>