<script setup>
const props = defineProps({
  text: String,
  color: String,
});
</script>
<script>
export default {
  methods: {
    onClick() {
      this.$emit("btn-click");
    },
  },
};
</script>
<template>
  <button @click="onClick" :style="{ background: color }" class="btn">
    {{ text }}
  </button>
</template>

<style></style>
