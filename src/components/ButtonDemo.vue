<template>
  <div>Button示例</div>
  <h1>示例1</h1>
  <div>
    <Button>您好</Button>
    <Button theme="button">您好</Button>
    <Button theme="link">您好</Button>
    <Button theme="text">您好</Button>
  </div>
  <h2>示例2</h2>
  <div>
    <div>
      <Button size="big">大大大</Button>
      <Button>普普通</Button>
      <Button size="small">小小小</Button>
    </div>
    <div>
      <Button theme="link" size="big">大大大</Button>
      <Button theme="link">普普通</Button>
      <Button theme="link" size="small">小小小</Button>
    </div>
    <div>
      <Button theme="text" size="big">大大大</Button>
      <Button theme="text">普普通</Button>
      <Button theme="text" size="small">小小小</Button>
    </div>
  </div>
  <h3>示例3</h3>
  <div>
    <div>
      <Button level="main">主要按钮</Button>
      <Button>普通按钮</Button>
      <Button level="danger">危险按钮</Button>
    </div>
    <div>
      <Button theme="link" level="main">主要链接按钮</Button>
      <Button theme="link">普通链接按钮</Button>
      <Button theme="link" level="danger">危险链接按钮</Button>
    </div>
    <div>
      <Button theme="text" level="main">主要文字按钮</Button>
      <Button theme="text">普通文字按钮</Button>
      <Button theme="text" level="danger">危险文字按钮</Button>
    </div>
  </div>
</template>

<script lang="ts">
import Button from "../lib/Button.vue";
export default {
  components: { Button },
  setup() {
    const onClick = () => {
      console.log("hi");
    };
    return { onClick };
  },
};
</script>

<style lang="scss" scoped></style>
