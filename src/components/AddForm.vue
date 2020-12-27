<template>
    <div>
        <form @submit="addNewTodo">
            <label>
                <input v-model="title" name="title" />
            </label>
            <input type="submit" value="Save" />
        </form>
    </div>
</template>

<script>
export default {
    name: 'AddForm',
    methods: {
        addNewTodo(e) {
            e.preventDefault()
            const newTodo = {
                title: this.title,
                completed: false,
            }
            this.$emit('add-todo', newTodo)
            this.title = ''
        },
    },
    data() {
        return {
            title: '',
        }
    },
}
</script>
