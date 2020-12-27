<template>
    <div id="app">
        <MainComponent msg="Welcome to Your Vue.js App" />
        <Todos :todos="todos" />
    </div>
</template>

<script>
import MainComponent from './components/MainComponent.vue'
import Todos from '@/components/Todos'

export default {
    name: 'App',
    components: {
        MainComponent,
        Todos,
    },
    data() {
        return {
            todos: [
                {
                    id: 1,
                    title: 'This is the title',
                    completed: false,
                },
                {
                    id: 2,
                    title: 'This is the title',
                    completed: true,
                },
                {
                    id: 3,
                    title: 'This is the title',
                    completed: true,
                },
                {
                    id: 4,
                    title: 'This is the title',
                    completed: true,
                },
                {
                    id: 5,
                    title: 'This is the title',
                    completed: true,
                },
                {
                    id: 6,
                    title: 'This is the title',
                    completed: true,
                },
            ],
        }
    },
}
</script>
