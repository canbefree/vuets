<template>
  <div class="neo-items">
    <img
      class="neo-items-img"
      src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1572260937586&di=f3b2712f2f89c67b6ca8c3d68001ae45&imgtype=0&src=http%3A%2F%2Fpic1.16pic.com%2F00%2F03%2F69%2F16pic_369066_b.jpg"
    />
    <div class="neo-item-box">
      <div class="neo-title">
        标题123333333333333333333333333333333333333333333333333333333333333333333333
      </div>
      <div class="neo-detail">dsf</div>
      <div class="neo-lab">
        <span>标签</span>
        <span>标签</span>
      </div>
      <div class="neo-ext">
        <span>%1.99</span>
        <button>+</button>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import Vue from "vue";
export default Vue.extend({});
</script>

<style lang="less" scoped>
.neo-items {
  display: flex;
  img {
    flex-grow: 1;
    max-width: 100px;
  }
  .neo-item-box {
    flex-grow: 2;
  }
  .neo-title {
    display: inline;
    justify-content: flex-start;
    overflow: hidden;
  }
  .neo-detail {
    width: 100%;
    display: flex;
    justify-content: flex-start;
  }
  .neo-lab {
    display: flex;
    justify-content: flex-start;
  }

  .neo-ext {
    display: flex;
    justify-content: space-between;
  }
}
</style>