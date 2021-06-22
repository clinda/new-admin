<!--
 * @Author: clinda
 * @Date: 2021-06-22 15:17:41
 * @LastEditors: clinda
 * @LastEditTime: 2021-06-22 17:33:01
-->

<template>
  <div class="page-style">
    <component-one :father-num="father" :father-num2="father2" @addC="addChild" />
    <el-button class="btn-part" type="" @click="addNum()">父传子</el-button>
    <div class="btn-part">子传来的值child:{{ child }}</div>
  </div>
</template>

<script>
import componentOne from './components/component-one.vue'

export default {
  name: 'Test',
  components: { componentOne },
  /* props: ['initialCounter'], */
  data() {
    return {
      /*  propNum: 1,
      computedNum: 2,
      watchNum: 3, */
      child: 0,
      father: 0,
      father2: 1
    }
  },
  computed: {},
  watch: {},
  methods: {
    addNum() {
      this.father += 1
      console.log(this.father, '父+1')
    },
    addChild(a) {
      console.log(a, 'ssss')
      /*  a += 1 */
      this.child = a
    }
  }
}
</script>
<style lang="scss" scoped>
  .page-style {
    height: 100%;
    width: 100%;
    .btn-part {
      background-color: #83b158;
      margin-left: 30px;
      margin-top: 30px;
      width: auto;
      height: auto;
    }
  }
</style>
