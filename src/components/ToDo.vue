<template>
  <tr class="to-do">
    <td><span :class="{ complete: completed }" @click="$emit('on-toggle')">{{ title }}</span></td>
    <td class="action-buttons">
      <button class="muted-button" @click="$emit('on-remove')">Remove</button>
    </td>
  </tr>
</template>

<script>
export default {
  name: 'ToDo',
  props: {
    title: String,
    completed: Boolean
  }
}
</script>

<style scoped>
  .to-do:hover {
    background: #eee;
  }

  .complete {
    text-decoration: line-through;
    color: #888;
  }

  .action-buttons {
    text-align: right;
  }
  .action-buttons button {
    margin: 0 2px;
  }
</style>