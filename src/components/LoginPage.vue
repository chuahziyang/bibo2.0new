<template>
  <v-app>
    <Header />
    <v-main>
      <v-container fluid fill-height>
        <v-layout align-center justify-center>
          <v-flex xs12 sm8 md4>
            <v-card v-if="!this.showRegister" class="elevation-12">
              <v-toolbar dark color="primary">
                <v-toolbar-title>Bibo-App</v-toolbar-title>
              </v-toolbar>
              <v-card-text>
                <v-form>
                  <v-text-field
                    v-model="user"
                    name="login"
                    label="Login"
                    type="text"
                  ></v-text-field>
                  <v-text-field
                    v-model="pass"
                    id="password"
                    name="password"
                    label="Password"
                    type="password"
                  ></v-text-field>
                </v-form>
              </v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn @click="login()" color="primary">Login</v-btn>
                <v-btn @click="register()" color="primary">Register</v-btn>
              </v-card-actions>
            </v-card>
            <!-- REGISTER COMPONENTS -->
            <v-card v-if="this.showRegister" class="elevation-12">
              <v-toolbar dark color="primary">
                <v-toolbar-title>Register</v-toolbar-title>
              </v-toolbar>
              <v-card-text>
                <v-form>
                  <v-text-field
                    v-model="persid"
                    name="PERSID"
                    label="PERSID"
                    type="text"
                  ></v-text-field>
                  <v-text-field
                    v-model="registerpass"
                    id="password"
                    name="password"
                    label="Password"
                    type="password"
                  ></v-text-field>
                  <v-text-field
                    v-model="confirmpass"
                    id="Confirm Password"
                    name="Confirm Password"
                    label="Confirm Password"
                    type="password"
                  ></v-text-field>
                  <v-text-field
                    v-model="authpass"
                    id="authpass"
                    name="authpass"
                    label="Authentication Password"
                    type="password"
                  ></v-text-field>
                </v-form>
              </v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn
                  v-if="!this.showRegister"
                  @click="login()"
                  color="primary"
                  >Login</v-btn
                >
                <v-btn
                  v-if="!this.showRegister"
                  @click="register()"
                  color="primary"
                  >Register</v-btn
                >
                <v-btn
                  v-if="this.showRegister"
                  @click="registeruser()"
                  color="primary"
                  >Submit</v-btn
                >
              </v-card-actions>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import Header from "./Header.vue";
export default Vue.extend({
  components: { Header },
  name: "LoginPage",
  data() {
    return {
      user: "",
      pass: "",
      showRegister: false,
    };
  },
  methods: {
    send() {
      console.log(this.user + "\n" + this.pass);
    },
    register() {
      this.showRegister = true;
    },
  },
});
</script>
