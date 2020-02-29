<template>
    <div class="item" v-bind:class="{ completed: item.completed}">
      <h2>{{ item.title }}</h2>
      <button v-if="!item.completed" @click="removeItem">Zrobione</button>
    </div>
</template>

<script>
  export default {
    name: "TodoItem",
    props: ['item'],
    data() {
      return {

      }
    },
    methods: {
      removeItem() {
        this.$emit('removeClicked', this.item.id)
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
</style>