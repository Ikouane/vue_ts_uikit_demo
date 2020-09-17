<template>
  <div class="ui-modal" :style="`
        --color-tint: ${ColorTint}
    `">
    <slot>请填写内容</slot>
  </div>
</template>
<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class UIModal extends Vue {
  @Prop(String) private msg: string | undefined;
  @Prop(String) private color: string | undefined;

  get ColorTint() {
    if (this.color) return this.color;
    else return "#2d8cf0";
  }
}
</script>
<style lang="stylus" scoped>
.ui-modal {
  background-color: var(--color-tint);
}
</style>