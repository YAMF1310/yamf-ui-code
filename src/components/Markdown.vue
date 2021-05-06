<template>
  <article class="markdown-body" v-html="content"></article>
</template>

<script lang="ts">
export default {
  props: {
    content: {
      type: String,
      requirted: true,
    },
  },
};
</script>

<style lang="scss" scoped></style>
