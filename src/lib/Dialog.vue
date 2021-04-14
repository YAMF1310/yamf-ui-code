<template>
  <template v-if="visible">
    <Teleport to="body">
      <div @click="OnClickOverLay" class="yamf-dialog-overlay"></div>
      <div class="yamf-dialog-wrapper">
        <div class="yamf-dialog">
          <header>
            <slot name="title" /><span
              @click="close"
              class="yamf-dialog-close"
            ></span>
          </header>
          <main>
            <slot name="content" />
          </main>
          <footer>
            <Button @click="ok" level="main">ok</Button>
            <Button @click="cancel">Cancel</Button>
          </footer>
        </div>
      </div>
    </Teleport>
  </template>
</template>

<script>
import Button from "./Button.vue";
export default {
  props: {
    title: {
      type: String,
      default: "提示",
    },
    visible: { type: Boolean, default: false },
    closeOnClickOverLay: {
      type: Boolean,
      default: true,
    },
    ok: {
      type: Function,
    },
    cancel: {
      type: Function,
    },
  },
  components: { Button },
  setup(props, context) {
    const close = () => {
      context.emit("update:visible", false);
    };
    const OnClickOverLay = () => {
      if (props.closeOnClickOverLay) {
        close();
      }
    };
    const ok = () => {
      if (props.ok?.() !== false) {
        close();
      }
    };
    const cancel = () => {
      context.emit("cancle");
      close();
    };
    return { close, OnClickOverLay, ok, cancel };
  },
};
</script>

<style lang="scss">
$radius: 4px;
$border-color: #d9d9d9;
.yamf-dialog {
  background: white;
  border-radius: $radius;
  box-shadow: 0 0 3px fade_out(black, 0.5);
  min-width: 15em;
  max-width: 90%;
  &-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: fade_out(black, 0.5);
    z-index: 10;
  }
  &-wrapper {
    position: fixed;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    z-index: 11;
  }
  > header {
    padding: 12px 16px;
    border-bottom: 1px solid $border-color;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 20px;
  }
  > main {
    padding: 12px 16px;
  }
  > footer {
    border-top: 1px solid $border-color;
    padding: 12px 16px;
    text-align: right;
  }
  &-close {
    position: relative;
    display: inline-block;
    width: 16px;
    height: 16px;
    cursor: pointer;
    &::before,
    &::after {
      content: "";
      position: absolute;
      height: 1px;
      background: black;
      width: 100%;
      top: 50%;
      left: 50%;
    }
    &::before {
      transform: translate(-50%, -50%) rotate(-45deg);
    }
    &::after {
      transform: translate(-50%, -50%) rotate(45deg);
    }
  }
}
</style>
