<template>
  <div :class="[task.reminder ? 'reminder' : 'reminder-false', 'task d-flex justify-content-between align-items-center py-2 px-3']">
    <div>
      <h5>{{ task.text }}</h5>
      <p class="mb-0">{{ task.day }}</p>
    </div>
    <div class="">
      <button @click="onDelete(task.id)" class="btn text-danger delete-icon"><i class="far fa-trash-alt"></i></button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
  methods: {
    onDelete(id) {
      this.$emit('delete-task', id)
    }
  },
};
</script>

<style scoped>
.task {
  background-color: rgb(234, 241, 241);
  margin-bottom: 8px;
}
 .delete-icon {
      font-size: 20px;
      transition: all 0.3s ease;
  }

  .delete-icon:hover {
      color: rgb(95, 175, 212) !important;
  }

  .reminder {
    border-left: 3px solid #2cceff;
  }
  .reminder-false {
    border-left: 3px solid gray;
  }
</style>