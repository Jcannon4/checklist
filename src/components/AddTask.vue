<template>
  <div>
    <form @submit="addTask">
      <input
        type="text"
        v-model="title"
        name="title"
        placeholder="Add a Task"
      />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
export default {
  name: 'AddTask',
  data() {
    return {
      title: '',
    };
  },
  methods: {
    addTask() {
      const newTask = {
        id: 0,
      };
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
}
input[type='text'] {
  flex: 10;
  padding: 5px;
}
input [type='submit'] {
  flex: 2;
}
</style>
