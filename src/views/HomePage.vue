<script>
import AppHeader from '../components/AppHeader.vue';
import AppFooter from '../components/AppFooter.vue';
export default {
    name: 'HomePage',
    components: {
        AppHeader,
        AppFooter
    }
}

</script>
        
<template>
    <div>
        <AppHeader></AppHeader>
        <h1>Home Page</h1>
        <AppFooter></AppFooter>
    </div>
</template>


<style lang="scss" scoped></style>