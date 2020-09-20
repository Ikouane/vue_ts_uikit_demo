<template>
  <button
    class="ui-btn"
    @click.stop="onClickBtn"
    :disabled="disabled"
    :class="{
      'ui-btn-xsmall': xsmall,
      'ui-btn-small': small,
      'ui-btn-large': large,
      'ui-btn-xlarge': xlarge,
      'ui-btn-tile': tile,
      'ui-btn-rounded': rounded,
      'ui-btn-circle': circle,
      'ui-btn-disabled': disabled,
    }"
    :style="`
      --color-tint: ${TintColor};
      --font-color: ${FontColor};
    `"
  >
    <slot>Button</slot>
  </button>
</template>
<script lang="ts">
// import { Component, Emit, Prop, Vue } from "vue-property-decorator";
import { defineComponent } from "vue";

// @Component
// export default class UIButton extends Vue {
//   @Prop(Boolean) private large: boolean | undefined;
//   @Prop(Boolean) private xlarge: boolean | undefined;
//   @Prop(Boolean) private small: boolean | undefined;
//   @Prop(Boolean) private xsmall: boolean | undefined;
//   @Prop(Boolean) private tile: boolean | undefined;
//   @Prop(Boolean) private rounded: boolean | undefined;
//   @Prop(Boolean) private circle: boolean | undefined;
//   @Prop(Boolean) private disabled: boolean | undefined;
//   @Prop(String) private color: string | undefined;
//   @Prop(String) private fontColor: string | undefined;

//   @Emit("click")
//   private emitClickEvent(event: MouseEvent) {
//     //console.log("事件处理函数", event);
//   }

//   private onClickBtn(event: MouseEvent) {
//     if (!this.disabled) this.emitClickEvent(event);
//     else console.log("按钮已禁用");
//   }

//   get TintColor() {
//     if (this.color) return this.color;
//     else return "#2d8cf0";
//   }

//   get FontColor() {
//     if (this.fontColor) return this.fontColor;
//     else return "#17233D";
//   }
// }
export default defineComponent({
  props: {
    large: Boolean,
    xlarge: Boolean,
    small: Boolean,
    xsmall: Boolean,
    tile: Boolean,
    rounded: Boolean,
    circle: Boolean,
    disabled: Boolean,
    color: String,
    fontColor: String,
  },
  computed: {
    TintColor(): string {
      if (this.color) return this.color;
      else return "#2d8cf0";
    },

    FontColor(): string {
      if (this.fontColor) return this.fontColor;
      else return "#17233D";
    },
  },
  methods: {
    onClickBtn(event: MouseEvent) {
      // if (!this.disabled) console.log("按钮被点击", event);
      // else {
      //   console.log("按钮已禁用", event);
      // }
    },
  },
});
</script>
<style lang="stylus" scoped>
resize(minWidth, height, paddingLR, fontSize) {
  min-width: minWidth;
  height: height;
  padding: 0 paddingLR;
  font-size: fontSize;

  &.ui-btn-rounded, &.ui-btn-circle {
    border-radius: (@height / 2);
  }

  &.ui-btn-circle {
    width: @height;
    min-width: 0;
    padding: 0;
  }
}

.ui-btn {
  min-width: 64px;
  height: 36px;
  padding: 0 16px;
  border: none;
  border-radius: 4px;
  color: var(--font-color);
  background-color: var(--color-tint); // var(--color-tint,#2d8cf0)
  font-size: 0.875rem;
  font-weight: 500;
  letter-spacing: 0.09em;
  outline: none; // 去除点击时的蓝色边框
  cursor: pointer;
  user-select: none; // 拖动时不选中文本
  transition: all 0.2s ease-in-out;

  &.ui-btn-xsmall {
    resize(36px, 20px, 9px, 0.625rem);
  }

  &.ui-btn-small {
    resize(50px, 28px, 12px, 0.75rem);
  }

  &.ui-btn-large {
    resize(78px, 44px, 19px, 0.875rem);
  }

  &.ui-btn-xlarge {
    resize(92px, 52px, 23px, 1rem);
  }

  &.ui-btn-tile {
    border-radius: 0;
  }

  &.ui-btn-rounded, &.ui-btn-circle {
    border-radius: (@height / 2);
  }

  &.ui-btn-circle {
    width: @height;
    min-width: 0;
    padding: 0;
  }

  &.ui-btn-disabled {
    background-color: #f5f5f5;
    cursor: not-allowed;
    color: #c5c8ce;
  }

  &.ui-btn-disabled:hover {
    filter: brightness(100%);
  }

  &:hover {
    filter: brightness(120%);
  }

  &:active {
    filter: brightness(80%);
  }
}
</style>