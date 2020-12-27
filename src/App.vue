<template>
    <div id="app">
        <NavBarHeader />
        <div id="nav">
            <router-link to="/">Homewww</router-link> |
            <router-link to="/about">About</router-link>
        </div>
        <router-view />
    </div>
</template>

<script>
import NavBarHeader from '@/components/Layout/NavBarHeader'

export default {
    components: {
        NavBarHeader,
    },
}
</script>
