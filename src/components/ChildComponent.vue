<template>
  <div>
    <h2>Child Component</h2>
    <p>{{ message }}</p>
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";

// Define a reactive property
const message = ref("");
</script>
