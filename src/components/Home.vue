<template>
  <v-main>
    <v-container fluid>
      <v-row>
        <v-col align="center" justify="center" cols="12">
          <blockquote>
            &#8220;Welcome {{validUserName}}!&#8221;
            <footer>
              <small>
                <em>&mdash;Subscription Alert.</em>
              </small>
            </footer>
          </blockquote>
        </v-col>
      </v-row>
    </v-container>

    <v-container fluid>
      <v-row
        align="center"
        justify="center"
      >
        <v-col 
          cols="12"
            sm="10"
            md="10"
        >
          <v-card class="elevation-2">
            <v-container
              fluid
              grid-list-md
            >
              <v-row>
                <v-col>
                  <v-card>
                    <v-img
                      :src="require('@/assets/images/Netflix.jpg')" height="100px">
                    </v-img>
                    <v-img
                      :src="require('@/assets/images/WoW.jpg')" height="100px">
                    </v-img>
                  </v-card>
                </v-col>                <v-col>
                  <v-card>
                    <v-img
                      :src="require('@/assets/images/Twitch.jpg')" height="100px">
                    </v-img>
                  </v-card>
                </v-col>
                <v-col>
                  <v-card>
                     <v-img
                      :src="require('@/assets/images/DisneyPlus.jpg')" height="100px">
                    </v-img>
                  </v-card>
                </v-col>
                <v-col>
                  <v-card>
                     <v-img
                      :src="require('@/assets/images/Hulu.jpg')" height="100px">
                    </v-img>
                  </v-card>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<script>
  import router from '../router';
  export default {
    name: 'Home',
    data: () => ({
      validUserName: "Guest"
    }),
    mounted() {
      this.getUser();
    },
    methods: {
      viewUsers() {
        router.push('/user-list');
      },
      viewSubscriptions() {
        router.push('/subscription-list');
      },

      getUser() {
        if (localStorage.getItem("isAuthenticates")
          && JSON.parse(localStorage.getItem("isAuthenticates")) === true) {
          this.validUserName = JSON.parse(localStorage.getItem("log_user"));
        }
      }
    }
  }
  
</script>