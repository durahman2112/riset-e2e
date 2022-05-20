<template>
  <v-container fill-height fluid class="primary">
    <v-row align="center" justify="center">
      <v-card min-width="400" max-width="500" rounded="lg" elevation="0">
        <v-card-title> Login </v-card-title>
        <v-card-text>
          <v-form ref="form" v-model="valid" lazy-validation>
            <v-text-field
              v-model="email"
              :rules="emailRules"
              label="E-mail"
              required
            ></v-text-field>
            <v-text-field
              v-model="password"
              :rules="passwordRules"
              label="Password"
              :type="showPassword ? '' : 'password'"
              :append-icon="showPassword ? 'mdi-eye-off' : 'mdi-eye'"
              @click:append="showPassword = !showPassword"
              required
            ></v-text-field>
            <v-btn :disabled="!valid" color="primary" block class="mr-4" @click="login">
              Login
            </v-btn>
            <!-- <v-btn :disabled="!valid" color="success" class="mr-4" @click="validate">
              Validate
            </v-btn>

            <v-btn color="error" class="mr-4" @click="reset"> Reset Form </v-btn>

            <v-btn color="warning" @click="resetValidation"> Reset Validation </v-btn> -->
          </v-form>
        </v-card-text>
      </v-card>
      <!-- <v-col>
      </v-col> -->
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    valid: true,
    password: "",
    passwordRules: [(v) => !!v || "Password is required"],
    email: "",
    emailRules: [
      (v) => !!v || "E-mail is required",
      (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
    ],
    showPassword: false,
  }),

  methods: {
    validate() {
      this.$refs.form.validate();
    },
    reset() {
      this.$refs.form.reset();
    },
    resetValidation() {
      this.$refs.form.resetValidation();
    },
    login() {
      console.log("login");
    },
  },
};
</script>

<style></style>
