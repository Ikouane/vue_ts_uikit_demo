<template>
  <div>
    <div class="flex">
      <div class="modal-group"></div>
      <div class="group-title">按钮</div>
      <div class="btn-group">
        <UIButton @click="ClickMe" class="btn" xsmall>超小</UIButton>
        <UIButton @click="ClickMe" class="btn" small>小</UIButton>
        <UIButton @click="ClickMe" class="btn">正常</UIButton>
        <UIButton @click="ClickMe" class="btn" large>大</UIButton>
        <UIButton @click="ClickMe" class="btn" xlarge>超大</UIButton>
        <br />
        <UIButton @click="ClickMe" class="btn" tile>矩形</UIButton>
        <UIButton @click="ClickMe" class="btn" rounded>半圆</UIButton>
        <UIButton @click="ClickMe" class="btn" circle>圆</UIButton>
        <br />
        <UIButton @click="ClickMe" class="btn" disabled>禁用</UIButton>
        <br />
        <UIButton @click="ClickMe" class="btn" color="gray">灰色背景</UIButton>
        <UIButton @click="ClickMe" class="btn" fontColor="#fff">白色字体</UIButton>
        <br />
        <UIButton @click="ClickMe" class="btn">无边框</UIButton>
      </div>
    </div>
  </div>
</template>


<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import UIButton from "@/components/UIKit/UIButton.vue";
import UIModal from "@/components/UIKit/UIModal.vue";

@Component({
  components: { UIButton, UIModal },
})
export default class Home extends Vue {
  private ClickMe(event: MouseEvent) {
    console.log(`按钮被点击了,${event}`);
  }
}
</script>


<style lang="stylus" scope>
.flex {
  display: flex;
  justify-content: center;
  width: 100%;
  flex-direction: column;

  .btn {
    margin: 10px;
  }
}
</style>