<template>
  <div id="container">
    <div id="search-bar">
      <search-bar></search-bar>
    </div>
    <div id="main">
      <div id="nav">
        <ul>
          <li>dfdf</li>
          <li>dfdf</li>
          <li>dfdf</li>
          <li>dfdf</li>
          <li>dfdf</li>
        </ul>
      </div>

      <div id="content">
        <!-- 分类标题 -->
        <div class="title">
          <img />
        </div>
        <div class="list">
            <item-box></item-box>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import SearchBar from "@/components/searchbar/index.vue";
import ItemBox from "@/components/itembox/index.vue";
@Component({
  components: {
    SearchBar,
    ItemBox
  }
})
export default class Classification extends Vue {
  @Prop() private msg!: string;
}
</script>

<style lang="less">
@import "../css/_variable.less";

#container {
  display: flex;
  flex-direction: column;
}

#search-bar {
  margin-top: @min-size*10;
  margin-bottom: @min-size*10;
}
#main {
  flex-grow: 1;

  display: flex;
  align-items: stretch;

  #nav {
    width: @font-size*5;
    background-color: @color-bottom-last;
  }

  & li {
    padding: @min-size*10;
    background-color: @color-middle;
  }
}

#content {
  flex-grow: 1;
  .title {
    img {
      width: 100%;
      height: 100px;
    }
  }
}
</style>