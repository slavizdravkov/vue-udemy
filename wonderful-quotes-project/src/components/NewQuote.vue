<template>
    <div class="row">
        <form class="col">
            <div class="col-sm-8 offset-sm-2 col-xs-12 col-md-6 offset-md-3 form-group">
                <label>Quote</label>
                <textarea class="form-control" rows="3" v-model="quote"></textarea>
            </div>
            <div class="col-sm-8 offset-sm-2 col-xs-12 col-md-6 offset-md-3 form-group">
                <button class="btn btn-primary" @click.prevent="newQuote" :disabled="isDisabled">New Quote</button>
            </div>
        </form>
    </div>
</template>

<script>
    import { eventBus } from '../main'
    export default {
        props: ['isExceedQuotes'],
        data () {
            return {
                quote: '',
            }
        },

        computed: {
            isDisabled () {
                console.log(this.isExceedQuotes);
                return this.isExceedQuotes || !this.quote;
            }
        },

        methods: {
            newQuote () {
                eventBus.$emit('addNewQuote', this.quote);
                this.quote = '';
            }
        },
    }
</script>

<style scoped>

</style>
