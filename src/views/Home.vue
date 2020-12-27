<template>
    <div id="app">
        <AddForm v-on:add-todo="addNewTodoList" />
        <MainComponent msg="Welcome to Your Vue.js App" />
        <Todos :todos="todos" v-on:del-todo="deleteTodo" />
    </div>
</template>

<script>
import MainComponent from '../components/MainComponent.vue'
import Todos from '@/components/Todos'
import AddForm from '@/components/AddForm'
import axios from 'axios'

export default {
    name: 'Home',
    components: {
        MainComponent,
        Todos,
        AddForm,
    },
    methods: {
        deleteTodo(id) {
            axios
                .delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
                .then(
                    () =>
                        (this.todos = this.todos.filter(
                            (todo) => todo.id !== id
                        ))
                )
                .catch((err) => console.log(err))
        },
        addNewTodoList(newTodo) {
            const { title, completed } = newTodo
            axios
                .post('https://jsonplaceholder.typicode.com/todos', {
                    title,
                    completed,
                })
                .then((res) => (this.todos = [...this.todos, res.data]))
                .catch((err) => console.log(err))
        },
    },
    data() {
        return {
            todos: [],
        }
    },
    created() {
        axios
            .get('https://jsonplaceholder.typicode.com/todos?_limit=1')
            .then((response) => (this.todos = response.data))
            .then((json) => console.log(json))
    },
}
</script>
