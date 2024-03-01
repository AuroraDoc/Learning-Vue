<template>
    <div class="todoListContainer">
        
        <h2>Todos:</h2>
        <br>
        <ul>
            <li v-for="(todoItem, index) in todoItemList">
                {{ todoItem }} 
                <button @:click="removeItem" style="background-color: black; color: red; font-weight: bold; border-radius: 25%;">X</button>
            </li>
        </ul>
    </div>
</template>

<script setup>

const emit = defineEmits(['removedItem'])

const props = defineProps({
    todoItemList: {
        type: Array,
        required: true
    }
})

const removeItem = (index) => {
    emit('removedItem', index)
}

</script>