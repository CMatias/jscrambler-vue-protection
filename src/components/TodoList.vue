<template>
<div>
  <p>
      Total Todo Count <span class="badge">{{ todos.length }}</span>
  </p>
  <ul class="list-group">
    <todo v-on:remove-todo="removeTodo" v-for="todo in todos" :key="todo.title"  :todo.sync="todo"></todo>
  </ul>
</div>
</template>

<script>
import Todo from './Todo';

export default {
  props: ['todos'],
  components: {
    Todo,
  },
  methods: {
    removeTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },
  },
};
</script>
