<template>
  <div id="app">
    <!-- mutations -->
    <button @click="decrementCountAsync({amout:2})">-</button>
    <span>{{count}}</span>
    <button @click="incrementCountAsync">+</button>

    <hr />
    <p>{{completedTodos}}</p>
    <button @click="fetchDataAsync">FetchData</button>
  </div>
</template>

<script>
import Count from "./components/Count";
import { mapState, mapGetters, mapMutations, mapActions } from "vuex";
export default {
  name: "app",
  components: {
    Count
  },
  computed: mapGetters([
    "count",
    "completedTodos",
    "completedTodosCount",
    "getTodosById"
  ]),
  methods: mapActions([
    "incrementCountAsync",
    "decrementCountAsync",
    "fetchDataAsync"
  ])

  // methods: {
  //   incrementCount() {
  //     // 触发actions
  //     this.$store.dispatch("incrementCountAsync");
  //   },
  //   decrementCount(n) {
  //     // 触发actions
  //     this.$store.dispatch("decrementCountAsync", n);
  //   },
  //   fetchData() {
  //     // 触发actions
  //     this.$store.dispatch("fetchDataAsync");
  //   }
  // }

  // computed: {
  //   count() {
  //     return this.$store.getters.getCount;
  //   },
  //   completedTodos() {
  //     return this.$store.getters.completedTodos;
  //   },
  //   completedTodosCount() {
  //     return this.$store.getters.completedTodosCount;
  //   },
  //   getTodosById() {
  //     return this.$store.getters.getTodosById;
  //   }
  // }

  // 写法3
  // computed: {
  //   ...mapState(["count", "todos"]),
  //   other() {}
  // }

  // 写法2
  // computed: mapState({
  //   count: state => state.count,
  //   todos: state => state.todos
  // })

  // 写法1
  // computed: {
  //   count() {
  //     return this.$store.state.count;
  //   },
  //   todos() {
  //     return this.$store.state.todos;
  //   }
  // }
};
</script>

<style>
</style>
