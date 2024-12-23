<template>
  <div class="px-4 sm:px-6 lg:px-8 max-w-5xl mx-auto mt-12">
    <h1 class="text-base font-semibold text-gray-900 text-center mb-5">
      Add a Job Post
    </h1>
    <JobAddForm @user-added="handleJobAdded" />
  </div>
</template>

<script setup>
import JobAddForm from "@/components/JobAddForm.vue";
import { useRouter } from "vue-router";

const handleJobAdded = (newJobPost) => {
  console.log(newJobPost);
};
</script>
