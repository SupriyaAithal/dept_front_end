<template>
  <v-container>
    <v-layout row>
      <v-flex xs12 sm6 offset-sm3>
        <v-card>
          <v-card-text>
            <v-container>
              <form>
                <v-layout row>
                  <v-flex xs12>
                    <v-text-field
                      name="username"
                      label="Username"
                      id="username"
                      v-model="username"
                      type="username"
                      required></v-text-field>
                  </v-flex>
                </v-layout>
                <v-layout row>
                  <v-flex xs12>
                    <v-text-field
                      name="password"
                      label="Password"
                      id="password"
                      v-model="password"
                      type="password"
                      required></v-text-field>
                  </v-flex>
                </v-layout>
                <v-layout row>
                  <v-flex xs12>
                    <v-btn type="button" v-on:click="signin">Sign in</v-btn>
                  </v-flex>
                </v-layout>
                <v-layout row>
                  <v-flex xs12>
                    <v-btn flat>Forgot password</v-btn>
                  </v-flex>
                </v-layout>
              </form>
            </v-container>
          </v-card-text>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>


<script>
import axios from 'axios'
export default {
  data () {
    return {
      username: '',
      password: '',
      siteName: 'http://433d1107.ngrok.io'
    }
  },
  methods: {
    signin: function () {
      var data = {
        username: this.username,
        password: this.password
      }
      axios.post(this.siteName + '/users/signin', data)
      .then((res) => {
        console.log(res)
      })
      .catch((error) => {
        console.log(error)
      })
    }
  }
}
</script>
