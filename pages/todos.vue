<template>
  <div>
    <v-list-item v-for="(todo, i) in todos" :key="i">
      <input type="checkbox" :cheked="todo.done" @change="toggle(todo)" />
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
    </v-list-item>
    <v-text-field
      type="text"
      placeholder="task"
      @keyup.enter="addTodo"
    ></v-text-field>
  </div>
</template>

<script>
import { mapMutations } from "vuex";
export default {
  computed: {
    todos() {
      return this.$store.state.todos.list;
    },
  },
  methods: {
    addTodo(e) {
      this.$store.commit("todos/add", e.target.value);
    },
    ...mapMutations({
      toggle: "todos/toggle",
    }),
  },
};
</script>

<style scoped>
.done {
  text-decoration: line-through;
}
</style>