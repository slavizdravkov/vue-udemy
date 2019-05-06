<template>
    <div>
        <li class="list-group-item" style="cursor: pointer" @click="showDetails">
            Server #{{ server.id }}
        </li>
    </div>
</template>

<script>
import { eventBus } from '../../main';

export default {
    props: ['server'],
    methods: {
        showDetails () {
            eventBus.$emit('serverDetails', this.server);
        }
    }
}
</script>

<style scoped>

</style>
