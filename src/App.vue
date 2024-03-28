<script>
    import AppHeader from '@/components/AppHeader.vue'

    export default {
        name: "AppVue",
        components: {
            AppHeader
        }
    }
</script>

<template>
    <AppHeader />

    <RouterView />
</template>

<style lang="scss">
@use '@/assets/scss/app.scss' as *;

</style>