<template>
  <div id="app">
    <h2 class="title">
      黑马买买买-商城
      <p>
        <router-link to="/index">主页</router-link>
        <router-link to="/cart">购物车{{$store.getters.totalCount}}</router-link>
        <router-link to="/cart">购物车2----{{totalCount}}</router-link>
      </p>
    </h2>
    <router-view></router-view>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
export default {
  name: "app",
  // 把Vuex中的 getters 跟当前这个组件的计算属性 合并了，直接使用当前这个计算属性的对应方法 快速获取 vuex中的值
  
  computed: {
    // 使用对象展开运算符将 getter 混入 computed 对象中
    ...mapGetters(["totalCount"])
  }
};
</script>

<style>
.title {
  margin-top: 0;
  height: 200px;
  font-size: 100px;
  font-weight: 900;
  background-color: hotpink;
  color: white;
}
.title p {
  font-size: 20px;
}
.title p a {
  margin-right: 20px;
}
</style>
