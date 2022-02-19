<template>
  <div class="mt-3">
    <form @submit="onSubmit" action="">
      <div class="form-group">
        <label class="font-weight-bold" for="">Task</label>
        <input
          v-model="text"
          class="form-control"
          type="text"
          name="add_task"
          id="add_task"
          placeholder="Add Task"
        />
      </div>
      <div class="form-group">
        <label class="font-weight-bold" for="">Day & Time</label>
        <input
          v-model="day"
          class="form-control"
          type="text"
          name="add_day"
          id="add_day"
          placeholder="Add Day & Time"
        />
      </div>
      <div class="form-check">
        <input
          v-model="reminder"
          class="form-check-input"
          type="checkbox"
          value=""
          id="flexCheckChecked"
        />
        <label class="form-check-label" for="flexCheckChecked">
          Checked
        </label>
      </div>
      <div class="my-2">
          <button class="btn btn-block bg-dark text-white">Save Task</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTask",
  data() {
      return {
          text: '',
          day: '',
          reminder: false
      }
  },
  methods: {
      onSubmit(e) {
          e.preventDefault();
          if(!this.text) {
              alert('Please add a task')
              return
          }

          const newTask = {
              id: Math.floor(Math.random() * 100000),
              text: this.text,
              day: this.day,
              reminder: this.reminder
          }

          this.$emit('add-task', newTask);

          this.text = ''
          this.day = ''
          this.reminder = false
      }
  },
};
</script>

<style lang="scss" scoped>
</style>