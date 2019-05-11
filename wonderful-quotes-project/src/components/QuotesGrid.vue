<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)">{{ quote }}</app-quote>
    </div>
</template>

<script>
    import Quote from './Quote'
    import { eventBus } from '../main';

    export default {
        props: ['quotes'],

        components: {
            appQuote: Quote
        },

        methods: {
            deleteQuote () {
                eventBus.$emit('deleteQuote', this.index);
            }
        }
    }
</script>

<style scoped>

</style>
