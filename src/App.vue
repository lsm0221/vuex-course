<template>
  <div id="app">
    <!-- mutations -->
    <button @click="decrementCount({amount:2})">-</button>
    <span>{{count}}</span>
    <button @click="incrementCount">+</button>
  </div>
</template>

<script>
import Count from "./components/Count";
import { mapState, mapGetters, mapMutations } from "vuex";

export default {
  name: "app",
  components: { Count },
  computed: mapGetters([
    "count",
    "completedTodos",
    "completedTodosCount",
    "getTodosById"
  ]),
  methods: mapMutations(["incrementCount", "decrementCount"])
  // methods: {
  //   increment() {
  //     // 调用mutations 里的 incrementCount  第一个参数是store.js中的名字,第二个参数是值
  //     this.$store.commit("incrementCount");
  //   },
  //   decrement(n) {
  //     // 调用mutations 里的 decrenmentCount
  //     this.$store.commit("decrementCount", n);
  //   }
  // }
};
</script>

<style>
</style>