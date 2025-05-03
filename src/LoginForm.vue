<template>
    <v-card class="pa-4" max-width="400" outlined>
      <v-card-title class="headline">התחברות</v-card-title>
      <v-card-text>
        <v-form ref="form" @submit.prevent="login">
          <v-text-field
            v-model="username"
            label="שם משתמש"
            prepend-icon="mdi-account"
            outlined
            dense
            required
          />
          <v-text-field
            v-model="password"
            label="סיסמה"
            type="password"
            prepend-icon="mdi-lock"
            outlined
            dense
            required
          />
          <v-btn block color="primary" @click="login">התחבר</v-btn>
        </v-form>
      </v-card-text>
    </v-card>
  </template>
  
  <script>
  export default {
    name: "LoginForm",
    data() {
      return {
        username: "",
        password: "",
      };
    },
    methods: {
      login() {
        this.$emit("submit", { username: this.username, password: this.password });
      },
    },
  };
  </script>
  