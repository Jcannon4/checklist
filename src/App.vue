<template>
  <div id="app">
    <Header></Header>
    <AddTask v-on:add-task="addTask" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from './components/Todos';
import Header from './components/layout/Header';
import AddTask from './components/AddTask';
export default {
  name: 'App',
  components: { Todos, Header, AddTask },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'TODO ONE',
          completed: false,
        },
        {
          id: 2,
          title: 'TODO TWO',
          completed: true,
        },
        {
          id: 3,
          title: 'TOdo Three',
          completed: false,
        },
      ],
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id != id);
    },
    addTask(newTask) {
      this.todos = [...this.todos, newTask];
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover {
  background: #666;
}
</style>
