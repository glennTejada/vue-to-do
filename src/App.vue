<template>
  <div id="app">
  <div class="smaller-container">
      <div class="flex-row">
        <div class="flex-small one-fourth"></div>
        <div class="flex-small half">
          <ToDoList />
        </div>
        <div class="flex-small one-fourth"></div>
      </div>
  </div>
  </div>
</template>

<script>
import ToDoList from './components/ToDoList.vue'

export default {
  name: 'App',
  components: {
  ToDoList
  }
}
</script>

<style>
  .footer {
  font-size: 0.9em;
  margin-top: 40px;
  }

  .footer img {
  width: 13px;
  margin-bottom: -1px;
  }
</style>
