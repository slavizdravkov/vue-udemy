<template>
    <div class="container">
        <main-header></main-header>
        <hr>
        <div class="row">
            <main-servers :servers-count="10"></main-servers>
            <server-details></server-details>
        </div>
        <hr>
        <main-footer></main-footer>
    </div>
</template>

<script>
import Header from './components/Header'
import Footer from './components/Footer'
import Servers from './components/Servers'
import ServerDetails from './components/ServerDetails'

export default {
    components: {
        'main-header': Header,
        'main-footer': Footer,
        'main-servers': Servers,
        'server-details': ServerDetails
    }
}
</script>

<style lang="scss">
    @import "~bootstrap/scss/bootstrap";
</style>
