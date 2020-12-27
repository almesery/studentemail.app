<template>
    <div>
        <h3>{{ msg }}</h3>
    </div>
</template>

<script>
export default {
    name: 'MainComponent',
    props: {
        msg: String,
    },
}
</script>
