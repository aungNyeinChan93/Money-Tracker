<template>
  <section>
    <div class="container">
      <div class="card my-2 text-danger">{{ name.toUpperCase() }}</div>
    </div>
  </section>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  name: {
    type: String,
    required: true,
  },
});
</script>
