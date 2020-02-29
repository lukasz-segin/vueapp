<template>
  <div id="app">
    <div class="item">
      <p>Nowe todo: {{ newItem }}</p>
      <input type="text" placeholder="todo" v-model="newItem">
      <button @click="addItem">Dodaj</button>
    </div>
    <TodoItem v-on:removeClicked="removeItem" v-bind:item="item" v-for="item in items" v-bind:key="item.id" />
  </div>
</template>

<script>
import TodoItem from "./TodoItem";
export default {
  name: 'TodoAppComponent',
  data() {
    return {
      newItem: '',
      items: [
        {title: 'Zrobić zakupy', completed: true, id: 1},
        {title: 'Nagrać kurs', completed: false, id: 2}
      ]
    }
  },
  components: {
    TodoItem
  },
  methods: {
    addItem() {
      this.items.push({ title: this.newItem, completed: false, id: Math.random()});
      this.newItem = '';
    },
    removeItem(id) {
      const index = this.items.findIndex(el => el.id === id);
      this.items[index].completed = true;
    }
  }
}
</script>

<style scoped>
  .item {
    border: 1px solid chocolate;
    padding: 5px;
    margin: 5px;
  }
  .completed {
    opacity: 0.5;
  }
  .completed h2 {
    text-decoration: line-through;
  }
</style>
