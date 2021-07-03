<template>
  <section>
    <h2>Add a Task</h2>
    <form @submit.prevent="submitForm">
      <div class="form-group">
        <input
          class="form-control mb-3"
          type="text"
          id="taskId"
          placeholder="Task ID"
          v-model="enteredId"
        />
      </div>

      <div class="form-group">
        <input
          class="form-control mb-3"
          type="text"
          id="taskTitle"
          placeholder="Task Title"
          v-model="enteredTitle"
        />
      </div>

      <div class="form-group">
        <textarea
          rows="5"
          id="taskDescription"
          v-model="enteredDescription"
        ></textarea>
      </div>
      <button type="submit" class="btn btn-primary form-control mt-3">
        Add Task
      </button>
    </form>
  </section>
  <!-- Starting point for the components -->
  
</template>

<script>
import { ref, reactive, inject } from "vue";
import { useRouter } from "vue-router";
//import TasksList from './TasksList.vue';

export default {
  // components: {
  //   TasksList,
  // },
  setup() {
    const router = useRouter();
    const enteredTitle = ref("");
    const enteredId = ref("");
    const enteredDescription = ref("");
    let userData = reactive({});

    // const tasks = inject("tasks");
    const addTask = inject("addValues");
    function submitForm() {
      userData = {
        title: enteredTitle,
        description: enteredDescription,
        id: enteredId,
      };
      addTask(userData);

      router.push("/tasks-list");
    }
    return { submitForm, enteredTitle, enteredId, enteredDescription };
  },
};
</script>

<style scoped>
section {
  margin: 3rem auto;
  max-width: 40rem;
  padding: 1rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}
</style>
