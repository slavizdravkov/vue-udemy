<template>
    <div class="form-group">
        <label for="full-name">Full Name:</label>
        <input type="text" id="full-name" class="form-control" :value="value" @input="keyPressed">
    </div>
</template>

<script>
    export default {
        props: ['value'],
        methods: {
            keyPressed (event) {
                this.$emit('input', event.target.value);
            }
        }
    }
</script>

<style scoped>

</style>
