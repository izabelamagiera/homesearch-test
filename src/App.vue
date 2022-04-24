<template>
  <div class="container mx-auto bg-gray-100 p-24">
        <div class="inline">
            <Button text="Add / Save" @click="saveTask" />
            <Button text="Edit" @click="editTask" />
        </div>
  <TaskInput v-if="editMode" :tasks="tasks" :newTask="newTask" @add-newTask="saveNewTask" />
  <TaskList v-else :tasks="tasks" />
  </div>
</template>

<script>
import TaskInput from './components/TaskInput.vue'
import TaskList from './components/TaskList.vue'
import Button from './components/Button.vue'
export default {
  name: 'App',
  components: {
    Button,
    TaskList,
    TaskInput
  },
  data() {
    return {
      tasks:[],
      newTask: {},
      editMode: true
    }
  },
  watch: {
    tasks: {
      handler() {
        localStorage.setItem('tasks', JSON.stringify(this.tasks))
      },
      deep: true
    }
  },
  mounted() {
    this.tasks = [
      {
        text: 'This is first task'
      },
      {
        text: 'Second task on the list'
      },
      {
        text: 'Third lucky guess'
      }
    ]
    if (localStorage.getItem("tasks")){
    this.tasks = JSON.parse(localStorage.getItem("tasks"))
  }
    
  },
  methods: {
    saveTask() {
      if(Object.values(this.newTask).length !== 0 && this.newTask.constructor === Object) {
        this.tasks.push(this.newTask)
        this.newTask = {}
      }
        this.editMode = false    
    },
    saveNewTask() {
      if(Object.values(this.newTask).length !== 0 && this.newTask.constructor === Object) {
        this.tasks.push(this.newTask)
        this.newTask = {}
      }
    },
    editTask() {
      this.editMode = true
    }
  },
  created() {
  },
}
</script>

<style>
body {
  background-color: rgb(243 244 246);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: rgb(243 244 246);
}
</style>
