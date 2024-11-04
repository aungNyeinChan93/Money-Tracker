<template>
  <section>
    <div class="container">
      <div class="card my-2">
        <div class="card-header h5">
          Total amount :
          <span class="text-danger h4">{{ totalAmount }}</span> MMK
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  totalAmount: {
    type: Number,
    default: 0,
  },
});
</script>
