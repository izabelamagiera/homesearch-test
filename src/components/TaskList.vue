<template>
         <div>
             <div v-if="tasks.length > 0">
              <div class="w-96 p-4 border my-4 mx-auto text-left bg-gray-200" :tasks="tasks" v-for="(task, index) in tasks" :key="index">
                  {{task.text}}
              </div>
              </div>
              <div v-else class="w-96 p-4 border my-4 mx-auto text-left bg-orange-50 text-center">
                 You have no tasks saved
              </div>
        </div>

</template>

<script>
// import TaskInput from './TaskInput.vue'
export default {
  name: 'TaskList',
  props: {
      tasks: Array,
  },
  data() {
      return {
      }  
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>