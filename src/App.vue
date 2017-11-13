<template>
  <div id="app">
    <div class="page-header">
      <h1>Vue.js Todo App</h1>
    </div>

    <todo-list v-bind:todos="todos"></todo-list>
    <form v-on:submit.prevent="addNewTodo()">
        <div class="form-group">
            <input v-model="newTodoText" type="text" class="form-control" name="name" placeholder="Enter new Todo here">
        </div>
    </form>
  </div>
</template>

<script>
import TodoList from './components/TodoList';


export default {
  name: 'app',
  components: {
    TodoList,
  },
  data() {
    return {
      newTodoText: '',
      todos: [{
        title: 'Todo 1',
        done: false,
      }, {
        title: 'Todo 2',
        done: false,
      }, {
        title: 'Todo 3',
        done: false,
      }, {
        title: 'Todo 4',
        done: false,
      }],
    };
  },
  methods: {
    addNewTodo() {
      if (this.newTodoText.length > 0) {
        this.todos.push({
          title: this.newTodoText,
          done: false,
        });
        this.newTodoText = '';
      }
    },
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
