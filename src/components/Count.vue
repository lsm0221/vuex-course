<template>
  <div id="count">
    <div>
      <hr />
      <h1>Count.vue{{count}}</h1>
      <p>Count.vue{{todos}}</p>
    </div>
  </div>
</template>

<script>
import { mapState } from "vuex";
export default {
  name: "count",
  components: {},
  //写法3
  computed: mapState(["count", "todos"])
  //写法二:
  //   computed: mapState({
  //     count: state => state.count,
  //     todos: state => state.todos
  //   })
  // 写法一:
  //   computed: {
  //     count() {
  //       return this.$store.state.count;
  //     },
  //     todos() {
  //       return this.$store.state.todos;
  //     }
  //   }
};
</script>

<style>
</style>
