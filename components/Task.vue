<template>
  <div :class="`task ${task.done ? 'is-complete' : ''}`">
    <div class="content">{{ task.content }}</div>
    <div class="buttons">
      <button @click="toogleDone">{{ task.done ? 'Undo' : 'Done' }}</button>
      <button @click="removeTask" class="delete">Delete</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ['task'],
  methods: {
    toogleDone() {
      this.$store.commit('toggleTask', this.task)
    },
    removeTask() {
      this.$store.commit('removeTask', this.task)
    },
  },
}
</script>

<style></style>
