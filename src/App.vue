<script setup>
import InteractScreen from "./components/InteractScreen.vue";
import MainScreen from "./components/MainScreen.vue";
</script>

<template>
  <MainScreen
    v-if="statusMatch === 'default'"
    @onStart="onHandleBeforeStart($event)"
  />
  <InteractScreen v-if="statusMatch === 'match'" />
</template>
<script>
export default {
  data() {
    return {
      statusMatch: "default",
    };
  },
  methods: {
    onHandleBeforeStart(config) {
      console.log(config);
      this.statusMatch = "match";
    },
  },
};
</script>