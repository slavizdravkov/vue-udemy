<template>
    <div class="row mt-5">
        <div class="col-sm-12">
            <div class="progress">
                <div class="progress-bar progress-bar-striped bg-info" role="progressbar" :style="progressWidth" :aria-valuenow="count" :aria-valuemin="min" :aria-valuemax="max">{{ quotesCountLabel }}</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['min', 'max', 'count'],
        computed: {
            progressWidth () {
                return `width: ${this.count * (100 / this.max)}%`
            },

            quotesCountLabel () {
                if (this.count > 0) {
                    return this.count;
                }

                return '';
            }
        }
    }
</script>

<style scoped>

</style>
