<template>
  <div class="container-fluid">
    <div class="w-25 p-4 border mt-5 ml-5 rounded shadow">
      <div class="d-flex justify-content-between align-items-center">
      <Header title="Task Tracker" />
    <div>
      <Button buttonText="Add Task" background="#068eb7" color="white" />
    </div>
    </div>
    <div class="border p-2 my-3">
      <Tasks @delete-task="deleteTask" :tasks="tasks" />
    </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from './Header.vue';
import Button from './Button.vue';
import Tasks from './Tasks.vue';

export default {
  name: 'Home',
  components: {
    Header,
    Button,
    Tasks
},
  data () {
    return {
      tasks: []
    }
  },
  methods: {
    deleteTask(id) {
      this.tasks = this.tasks.filter((task) => task.id !== id)
    }
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: 'Doctors Appointment',
        day: 'March 1st at 2.30pm',
        reminder: true,
      },
      {
        id: 2,
        text: 'Meeting at school',
        day: 'March 1st at 11.30am',
        reminder: true,
      },
      {
        id: 3,
        text: 'Go for a walk',
        day: 'March 1st at 6.30pm',
        reminder: true,
      },
      {
        id: 4,
        text: 'Watching Tutorial',
        day: 'March 1st at 2.30pm',
        reminder: false,
      },
      {
        id: 5,
        text: 'Going to Sleep',
        day: 'March 1st at 2.30pm',
        reminder: true,
      },
    ]
  }
}
</script>
