<template>
  <div id="app">
    <Header></Header>
    <AddTask />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from './components/Todos';
import Header from './components/layout/Header';
import AddTask from './components/AddTask.vue';
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
</style>
