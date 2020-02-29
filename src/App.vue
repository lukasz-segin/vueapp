<template>
  <div>
    <h1>Todo App</h1>
    <TodoApp />
  </div>
</template>

<script>
  import Todo from "./components/TodoAppComponent";
  export default {
    name: 'app',
    data() {
      return{

      }
    },
    components: {
      TodoApp: Todo
    }
  }
</script>