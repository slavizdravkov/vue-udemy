<template>
    <div class="container">
        <main-header></main-header>
        <hr>
        <div class="row">
            <main-servers></main-servers>
            <server-details></server-details>
        </div>
        <hr>
        <main-footer></main-footer>
    </div>
</template>

<script>
import Header from './components/shared/Header'
import Footer from './components/shared/Footer'
import Servers from './components/server/Servers'
import ServerDetails from './components/server/ServerDetails'

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
