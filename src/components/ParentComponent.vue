<template>
  <div>
    <h1>Parent Component</h1>
    <ChildComponent :message="parentMessage" />
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";
import ChildComponent from "./ChildComponent.vue";

// Define a reactive property
const parentMessage = ref("Hello from parent");
</script>
