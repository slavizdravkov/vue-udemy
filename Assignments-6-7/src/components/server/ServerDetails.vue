<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="!server">{{ detailsStatus }}</p>
        <p v-else>Server ID: {{ server.id }}. Server Status: {{ server.status }}</p>
        <hr>
        <button class="btn btn-primary" @click="changeToNormal">Change to Normal</button>
    </div>
</template>

<script>
import { eventBus } from '../../main';

export default {
    data () {
        return {
            detailsStatus: 'Server Details are currently not updated',
            server: null
        }
    },
    created () {
        eventBus.$on('serverDetails', (server) => {
            this.server = server;
        })
    },
    methods: {
        changeToNormal () {
            this.server.status = 'Normal';
        }
    }
}
</script>

<style scoped>

</style>
