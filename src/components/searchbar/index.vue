<template>
  <div>
    <div class="neo-searchbar" v-bind:class="{focus:onfocus}">
      <div class="neo-searchbar-box">
        <label class="neo-search-box-icon" for="neo-search-input">
          <i class="fa fa-search"></i>
        </label>
        <input
          id="neo-search-input"
          v-model="text"
          class="neo-searchbar-input"
          placeholder="搜索"
          @blur="inputBlur"
        />
        <a class="neo-searchbar-remove" href="javascript:void(0)" v-bind:class="{show:text?false:true}" @click="removeText">
          <i class="fa fa-remove"></i>
        </a>
      </div>
      <a class="neo-searchbar-cancel" href="javascript:void(0)">取消</a>
      <label class="neo-searchbar-label" @click="inputFocus">
        <i class="fa fa-search"></i>
        <span>搜索</span>
      </label>
    </div>
  </div>
</template>
<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  data() {
    return {
      onfocus: true,
      text: null
    };
  },
  created() {},
  methods: {
    inputBlur: function() {
      console.log("blur");
      this.onfocus = false;
      this.inputFocus();
    },
    inputFocus: function() {
      console.log("focus");
      this.onfocus = true;
    },
    removeText: function() {
      this.text = null;
      this.inputFocus();
    },
    inputFocue: function() {
      let input = document.getElementById("neo-search-input");
      if (input) {
        input.focus();
      }
    }
  }
});
</script>
<style lang="less">
@import "../../../node_modules/font-awesome/less/font-awesome.less";
@input-line-height: 30px;
@input-line-width: 100%;
@label-absolute-top: 2px;
@input-border-size: 1px;
// @shadow: 5px 5px 3px grey;
@shadow: none;
@font-size: 16px;
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
.neo-searchbar {
  margin-left: @font-size;
  margin-right: @font-size;
  box-shadow: @shadow;
  font-size: @font-size;
  display: flex;
  align-items: center;
  position: relative;
  border-radius: @input-line-height / 3 @input-line-height / 3
    @input-line-height / 3 @input-line-height / 3;
  .neo-searchbar-box {
    border: @input-border-size solid black;
    border-radius: @input-line-height / 3 0 0 @input-line-height / 3;
    border-right: none;
    width: @input-line-width;
    position: relative;
    display: flex;
    justify-content: space-between;

    .neo-search-box-icon {
      line-height: @input-line-height;
      position: relative;
      top: @label-absolute-top;
      vertical-align: middle;
      width: @font-size*3;
    }
    .neo-searchbar-input {
      outline: none;
      border: none;
      // border-right: @input-border-size solid black;
      line-height: @input-line-height;
      flex-grow: 1;
    }
    .neo-searchbar-remove {
      &.show{
        display: none;
      }
      position: absolute;
      top: @label-absolute-top;
      right: 0px;
      top:20%;
      width: @font-size*2;
      color: black;
      text-decoration: none;
      border: none;
    }
  }

  .neo-searchbar-cancel {
    font-weight: 700;
    font-family: STXihei, sans-serif;
    color: rgb(4, 65, 27);
    text-decoration: none;
    text-decoration-color: rgb(27, 27, 29);
    width: @font-size*5;
    line-height: @input-line-height;
    background-color: rgb(26, 167, 125);
    border: @input-border-size solid rgb(31, 140, 190);
    border-radius: 0 @input-line-height / 3 @input-line-height / 3 0;
  }

  .neo-searchbar-label {
    font: $font-size sans-serif;
    background-color: white;
    border: @input-border-size solid black;
    border-radius: @input-line-height / 3 @input-line-height / 3
      @input-line-height / 3 @input-line-height / 3;
    width: 100%;
    z-index: 99;
    line-height: @input-line-height;
    position: absolute;
  }
  &.focus {
    .neo-searchbar-label {
      display: none;
    }
  }
}
</style>