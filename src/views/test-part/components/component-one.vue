<!--
 * @Author: clinda
 * @Date: 2021-06-22 16:10:52
 * @LastEditors: clinda
 * @LastEditTime: 2021-06-22 17:33:58
-->
<template>
  <div class="page-style">
    <div class="btn-part">
      <el-button type="" @click="addToF()">传值给父组件child+1</el-button>
      <div class="num-part">来自父组件的father :{{ fatherNum }},father2 :{{ fatherNum2 }}</div>
      <el-button type="">计算属性</el-button>
      <div class="num-part">等于father1加father2: {{ computedNum }}</div>
      <el-button type="">watch</el-button>
      <div class="num-part">{{ watchNum }}</div>
      <!--  <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    </div>
  </div>
</template>

<script>
/* import { component } from 'vue/types/umd' */

export default {
  name: 'ComponentOne',
  props: {
    fatherNum: {
      type: Number,
      default: 0
    },
    fatherNum2: {
      type: Number,
      default: 0
    }
  },
  data() {
    return {
      childNum: 0,
      /*  computedNum: 2, */
      watchNum: 3
    }
  },
  computed: {
    computedNum: function() {
      return this.fatherNum + this.fatherNum2
    }
  },
  watch: {},
  methods: {
    addToF() {
      console.log('触发')
      this.childNum += 1
      this.$emit('addC', this.childNum)
    }
  }
}
</script>
<style lang="scss" scoped>
  .page-style {
    height: 100%;
    width: 100%;
    .btn-part {
      margin-left: 30px;
      margin-top: 30px;
      width: auto;
      height: auto;
    }
    .num-part {
      margin: 10px;
    }
  }
</style>
