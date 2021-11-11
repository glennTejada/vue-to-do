<template>
  <div id="todo-list">
    <h1>To Do List</h1>
    <form @submit.prevent>
      <input type="text" v-model="newItem">
      <button @click="addNewItem()">Add to list</button>
    </form>
    <table id="list">
      <ToDo
        v-for="(todo, index) in todos"
        :key="index"
        :title="todo.title"
        :completed="todo.completed"
        @on-toggle="toggleToDo(todo)"
        @on-remove="removeToDo(todo)"
      />
    </table>
  </div>
</template>

<script>
import ToDo from './ToDo.vue'

export default {
  name: 'ToDoList',
  components: {
    ToDo
  },
  props: {
    itemTitle: String
  },
  data() {
    return {
      todos: [
        { title: 'Take out the trash', completed: true },
        { title: 'Email about party', completed: false }
      ]
    };
  },
  methods: {
    addNewItem() {
      if (this.newItem.length > 0) {
        this.todos.unshift({ title: this.newItem, completed: false })
      }
    },
    toggleToDo(todo) {
      todo.completed = !todo.completed
    },
    removeToDo(removedTodo) {
      this.todos = this.todos.filter (todo => todo != removedTodo)
    }
  }
}
</script>

<style>
  .heart {
    stroke: pink;
  }
</style>