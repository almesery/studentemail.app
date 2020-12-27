<template>
    <div
        class="todo-item"
        :class="todo.completed ? 'is-completed' : 'un-completed'"
        style="border: 1px solid #000"
    >
        <label>
            <input type="checkbox" v-on:change="markAsCompleted" />
        </label>
        <button @click="$emit('del-todo', todo.id)">Delete</button>
        <h3>{{ todo.title }}</h3>
        <h3>{{ todo.id }}</h3>
    </div>
</template>
<script>
export default {
    name: 'TodoItem',
    props: ['todo'],
    methods: {
        markAsCompleted() {
            this.todo.completed = !this.todo.completed
        },
    },
}
</script>
<style scoped>
.is-completed {
    background: blue;
}

.un-completed {
    background: red;
}
</style>
