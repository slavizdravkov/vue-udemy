<template>
    <div class="container">
        <app-progress :min="minQuotes" :max="maxQuotes" :count="quotesCount"></app-progress>
        <app-new-quote :is-exceed-quotes="isExceedQuotes"></app-new-quote>
        <app-quotes-grid :quotes="quotes"></app-quotes-grid>
        <div class="row mt-2">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">
                    Info: Click in a Quote to delete it!
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuotesGrid from './components/QuotesGrid'
    import NewQuote from './components/NewQuote'
    import Progress from './components/Progress'
    import { eventBus } from './main';

    export default {
        computed: {
            quotesCount () {
                return this.quotes.length;
            },
            isExceedQuotes () {
                return this.quotesCount >= this.maxQuotes
            }
        },
        data () {
            return {
                quotes: [
                    'First wonderful quote!'
                ],
                maxQuotes: 10,
                minQuotes: 0
            }
        },
        components: {
            appQuotesGrid: QuotesGrid,
            appNewQuote: NewQuote,
            appProgress: Progress
        },

        created() {
            eventBus.$on('addNewQuote', (quote) => {
                this.quotes.push(quote);
                if (this.quotes.length >= this.maxQuotes) {
                    eventBus.$emit('maxIsReached')
                }
            });
            eventBus.$on('deleteQuote', (index) => {
                this.quotes.splice(index, 1);
            })
        }
    }
</script>

<style lang="scss">
    @import "css/styles";
</style>
