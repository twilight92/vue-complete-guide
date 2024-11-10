<template>
  <div>
    <div v-for="user in users" :key="user">{{ user.title }}</div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      users: [],
    };
  },
  created() {
    const vm = this;
    axios
      .get("https://api.hnpwa.com/v0/news/1.json")
      .then((response) => {
        console.log(response);
        vm.users = response.data;
      })
      .catch((error) => {
        console.log(error);
      });
  },
};
</script>

<style></style>
