<template>
  <v-row justify="center">
    <v-col cols="12" sm="8" md="6" lg="4">
      <v-card>
        <v-card-title class="headline">Login</v-card-title>
        <v-card-text>
          <v-text-field
            v-model="email"
            label="Email Address "
            placeholder="your@email.com"
            type="email"
            :rules="[emailRule]"
            required
          ></v-text-field>
          
          <v-text-field
            v-model="password"
            label="Password"
            placeholder="Enter your password"
            type="password"
            :rules="[passwordRule]"
            required
          ></v-text-field>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions>
          <v-btn color="primary" @click="submitLogin" :disabled="formHasErrors">Login</v-btn>
          <v-spacer></v-spacer>
          <v-btn text>Forgot password?</v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: "",
      formHasErrors: false,
      emailRule: [(v) => !!v || "Email is required", (v) => /.+@.+\..+/.test(v) || "Enter a valid email"],
      passwordRule: [(v) => !!v || "Password is required", (v) => v.length >= 6 || "Password must be at least 6 characters long"]
    };
  },
  methods: {
    submitLogin() {
      if (this.$refs.form.validate()) {
        this.formHasErrors = false;
        // Proceed with login logic (call API, etc.)
        console.log("Logged in with", this.email, this.password);
      } else {
        this.formHasErrors = true;
      }
    }
  }
};
</script>

<style scoped>
.v-card {
  max-width: 400px;
  margin: 50px auto;
}
</style>
