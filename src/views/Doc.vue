import Topnav from '@/components/Topnav.vue';
<template>
  <div>
    <Topnav />
    <div class="content">
      <aside>边拦</aside>
      <main>主要内容</main>
    </div>
  </div>
</template>

<script lang="ts">
import Topnav from "../components/Topnav.vue";
export default {
  components: { Topnav },
};
</script>

<style lang="scss" scoped></style>
