<template>
  <v-container grid-list-md>
    <v-row align="center" justify="center">
      <v-col cols="12" sm="6" md="4" lg="4">
        <v-card class="mx-auto elevation-6">
          <v-card-title>
            <span align="center" class="headline">Welcome to SubAlert</span>
          </v-card-title>

  <form @submit.prevent="handleSubmit">
      <h3> Forgot Password</h3>

      <div class ="form-group">

        <label>Email></label>
        <input type="email" class="form-control" v-model="email" placeholder="Email"/>

      </div>

      <button class="btn btn-primary btn-block">Submit</button>

  </form>

            </v-form>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import axios from 'axios'

export default {

    name: 'ForgotPassword',

    data()  {

        return {

            email: ''
        }

    },
    methods: {
        async handleSubmit() {

            const reponse = await axios.post('ForgotPassword', {
                
                email: this.email

            });

            console.log(reponse);
    } 
}
}

</script>

<style>

</style>