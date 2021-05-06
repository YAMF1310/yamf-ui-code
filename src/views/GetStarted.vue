<template>
  <Markdown :content="GetStarted" />
</template>

<script lang="ts">
import GetStarted from "../markdown/get-started.md";
export default {
  setup() {
    return { GetStarted };
  },
};
</script>
