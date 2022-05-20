<template>
  <div class="home">
    <h1>Welcome to Your Vue.js App</h1>

    <v-btn color="primary" @click="throwError">Throw Error</v-btn>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {},
  methods: {
    throwError() {
      throw Error("Ini Error dur");
    },
  },
};
</script>
