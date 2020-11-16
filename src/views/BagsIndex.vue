<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="bag in bags">
      <h2> Color: {{  bag.color }}</h2>
      <p> Size: {{  bag.size }}</p>
      <p> Price: {{  bag.price }}</p>
    </div>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      message: "Index page!",
      bags: [],
    };
  },
  created: function () {
    axios.get("/api/bags").then((response) => {
      console.log("bags index", response);
      this.bags = response.data;
    });
  },
  methods: {},
};
</script>