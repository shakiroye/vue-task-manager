<script setup>
import Button from "./Button.vue";
const props = defineProps({
  title: String,
  showAddTask: Boolean,
});
</script>

<script>
export default {
  computed: {
    homePage() {
      if (this.$route.path === "/") {
        return true;
      } else {
        return false;
      }
    },
  },
};
</script>

<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      v-show="homePage"
      @btn-click="$emit('toggle-add-task')"
      :text="showAddTask ? 'Close' : 'Add'"
      :color="showAddTask ? 'red' : 'green'"
    />
  </header>
</template>

<style>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
