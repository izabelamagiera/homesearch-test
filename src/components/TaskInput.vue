<template>
      <div>
        <div v-if="tasks.length > 0">
          <div v-for="(task, index) in tasks" :key="index">
            <input class="w-96 p-4 border mt-4 task" type="text" id="task" v-model="task.text" @keyup.backspace="deleteTask(index)">
          </div>
        </div>
        <input class="w-96 p-4 border mt-4 newTask" type="text" id="newTask" v-model="newTask.text" @keyup.enter="addTask(index)" autofocus>
      </div>
             
</template>

<script>
export default {
  name: 'TaskInput',
    props: {
      tasks: Array,
      newTask: Object
  },
  emits: ['tasks', 'newTask', 'add-newTask'],
  data() {
      return {
      }
    
  },
  methods: {
      addTask() {
        this.$emit('add-newTask')
    },
      deleteTask(index) {
      this.tasks.splice(index, 1)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
