<template>
  <div class="user-form max-w-lg mx-auto p-6 bg-white rounded-lg shadow-md">
    <form @submit.prevent="handleSubmit" class="space-y-6">
      <div>
        <label for="title" class="block text-sm font-medium text-gray-700"
          >Job Title:</label
        >
        <input
          type="text"
          id="title"
          v-model="formData.title"
          required
          class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
        />
      </div>
      <div>
        <label for="email" class="block text-sm font-medium text-gray-700"
          >Email:</label
        >
        <input
          type="email"
          id="email"
          v-model="formData.email"
          required
          class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
        />
      </div>
      <div>
        <label for="description" class="block text-sm font-medium text-gray-700"
          >Description:</label
        >
        <textarea
          id="description"
          v-model="formData.description"
          required
          class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
        ></textarea>
      </div>
      <div>
        <label for="location" class="block text-sm font-medium text-gray-700"
          >Location:</label
        >
        <input
          type="text"
          id="location"
          v-model="formData.location"
          required
          class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
        />
      </div>
      <div>
        <button
          type="submit"
          class="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
        >
          Add a Job
        </button>
      </div>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();
const formData = ref({
  title: "",
  email: "",
  description: "",
  location: "",
});
// const emit = defineEmits(["jobAdded"]);
// const handleSubmit = () => {
//   console.log(formData.value);
//   emit("jobAdded", { ...formData.value });
//   emit('user-added', newJobData);
// };

const handleSubmit = () => {
  router.push({
    name: "/",
    query: {
      title: formData.value.title,
      email: formData.value.email,
      description: formData.value.description,
      location: formData.value.location,
    },
  });
};
</script>
