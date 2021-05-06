<template>
  <h2>Dialog示例</h2>
  <Demo :component="Dialog1Demo" />
</template>

<script lang="ts">
import Demo from "../components/Demo.vue";
import Dialog1Demo from "../components/Dialog1.demo.vue";
export default {
  components: { Demo, Dialog1Demo },
  setup() {
    return { Demo, Dialog1Demo };
  },
};
</script>

<style lang="scss" scoped></style>
