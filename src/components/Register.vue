<template>
  <v-container grid-list-md>
    <v-row align="center" justify="center">
      <v-col cols="12" sm="6" md="4" lg="4">
        <v-card class="mx-auto elevation-6">
          <v-card-title>
            <span align="center" class="headline">Welcome to SubAlert</span>
          </v-card-title>

    <form @submit.prevent="handleSubmit">
        <h3>Sign Up</h3>

        <div class="form-group">
            <label>Username</label>
            <input type="text" class="form-control" v-model="Username" placeholder="Username"/>
        </div>

        <div class="form-group">
            <label>Email</label>
            <input type="text" class="form-control" v-model="Email" placeholder="Email"/>
        </div>

        <div class="form-group">
            <label>Phone Number</label>
            <input type="text" class="form-control" v-model="PhoneNum" placeholder="PhoneNum"/>
        </div>

        <div class="form-group">
            <label>Address</label>
            <input type="text" class="form-control" v-model="Address" placeholder="Address"/>
        </div>

        <div class="form-group">
            <label>City</label>
            <input type="text" class="form-control" v-model="City" placeholder="City"/>
        </div>

        <div class="form-group">
            <label>State</label>
            <input type="text" class="form-control" v-model="State" placeholder="State"/>
        </div>

        <div class="form-group">
            <label>Zipcode</label>
            <input type="text" class="form-control" v-model="Zipcode" placeholder="Zipcode"/>
        </div>

        <div class="form-group">
            <label>Password</label>
            <input type="text" class="form-control" v-model="Password" placeholder="Password"/>
        </div>

        <div class="form-group">
            <label>Confirm Password</label>
            <input type="text" class="form-control" v-model="Confirm_Password" placeholder="Confirm_Password"/>
        </div>

        <button class="btn btn-primary btn-block">Sign Up</button>
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
        name: 'Register',
        data() {
            return {
                Username: '',
                Email: '',
                PhoneNum: '',
                Address: '',
                City: '',
                State: '',
                Zipcode: '',
                Password: '',
                Confirm_Password: ''

            }
        },
        methods: {
            handleSubmit(){
                const data = {
                    Username: this.Username,
                    Email: this.Email,
                    PhoneNum: this.PhoneNum,
                    Address: this.Address,
                    City: this.City,
                    State: this.State,
                    Zipcode: this.Zipcode,
                    Password: this.Password,
                    Confirm_Password: this.Confirm_Password
                };
               
               axios.post('https://nostalgic-lovelace-dc74e1.netlify.app/register', data)
                .then(
                    res => {
                        console.log(res)
                    }

                ).catch()
                    err => {
                        console.log(err)
                    }
            }
        }
    }
</script>

<style>

</style>
