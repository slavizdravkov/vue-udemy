<template>
    <div class="container">
        <form v-if="!isSubmitted">
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <app-full-name v-model="fullName"></app-full-name>

                    <div class="form-group">
                        <label for="email">E-mail:</label>
                        <input type="text" id="email" class="form-control" v-model="email">
                    </div>

                    <div class="form-group">
                        <label for="password">Password:</label>
                        <input type="password" id="password" class="form-control" v-model="password">
                    </div>

                    <div class="form-check form-check-inline">
                        <input
                            type="radio"
                            class="form-check-input"
                            id="store-data-yes"
                            v-model="storeData"
                            value="yes"
                        >
                        <label for="store-data-yes">Store Data (Yes)</label>
                    </div>

                    <div class="form-check form-check-inline">
                        <input
                            type="radio"
                            class="form-check-input"
                            id="store-data-no"
                            v-model="storeData"
                            value="no"
                        >
                        <label for="store-data-no">Store Data (No)</label>
                    </div>

                    <button type="submit" class="btn btn-primary" @click.prevent="submitted">Submit</button>
                    <!-- Exercise 1 -->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <!-- Full Name (First Name + Last Name) -->
                    <!-- Mail -->
                    <!-- Password -->
                    <!-- Store Data? Yes/No -->

                    <!-- Exercise 2 -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->

                    <!-- Exercise 3 -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="isSubmitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ fullName }}</p>
                        <p>Mail: {{ email }}</p>
                        <p>Password: {{ password }}</p>
                        <p>Store in Database?: {{ storeData }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import FullName from './components/FullName'
    export default {
        data() {
            return {
                fullName: '',
                email: '',
                password: '',
                storeData: 'no',
                isSubmitted: false
            }
        },
        methods: {
            submitted () {
                this.isSubmitted = true;
            }
        },
        components: {
            'app-full-name': FullName
        }
    }
</script>

<style lang="scss">
    @import "~bootstrap/scss/bootstrap.scss";
</style>
