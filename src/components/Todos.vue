<template>
    <div class="todo-page">
        <h3>Todo Lists</h3>
        <h3 v-for="todo in todos" :key="todo.id">
            <todo-item
                :todo="todo"
                v-on:del-todo="$emit('del-todo', todo.id)"
            />
        </h3>
    </div>
</template>
<script>
import TodoItem from '@/components/TodoItem'

export default {
    name: 'Todos',
    components: {
        TodoItem,
    },
    props: ['todos'],
}
</script>
