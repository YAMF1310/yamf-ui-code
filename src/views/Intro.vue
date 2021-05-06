<template>
  <Markdown :content="intro" />
</template>

<script lang="ts">
import intro from "../markdown/intro.md";
export default {
  setup() {
    return { intro };
  },
};
</script>
