<template>
  <Markdown :content="install" />
</template>

<script lang="ts">
import install from "../markdown/install.md";
export default {
  setup() {
    return { install };
  },
};
</script>
