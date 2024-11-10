<template>
  <div>
    ask
    <div v-for="item in fetchedAsk" :key="item">
      {{ item.title }}
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  computed: {
    ...mapGetters({
      fetchedAsk: "fetchedAsk",
    }),
    // #2
    // ...mapState({
    //     fetchedAsk: state => state.ask;
    // })

    // #1
    // ask() {
    //     return this.$store.state.ask;
    // }
  },
  created() {
    this.$store.dispatch("FETCH_ASK");
  },
};
</script>

<style></style>
