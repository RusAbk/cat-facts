<template>
  <div id="app">
    <Fact v-on:update="updFact">{{ factText }}</Fact>
  </div>
</template>

<script>
import Fact from "./components/Fact.vue";

export default {
  name: "app",
  components: {
    Fact
  },
  data() {
    return {
      factText: ""
    };
  },
  methods: {
    updFact() {
      this.axios
        .get("http://188.225.47.187/api/cats/random-fact.php")
        .then(response => {
          this.factText = response.data;
        });
    }
  },
  mounted() {
    this.updFact();
    // setInterval(this.updFact, 10000);
  }
};
</script>

<style>
#app {
  padding: 0;
  margin: 0;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
