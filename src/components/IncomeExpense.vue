<template>
  <section>
    <div class="container">
      <div class="card my-2 p-3">
        <div class="row">
          <div class="col-6 text-center">
            <divc class="text-muted h5">Income Amount</divc>
            <div class="text-primary">{{ income }} mmk</div>
          </div>
          <div class="col-6 text-center">
            <div class="text-muted h5">Expense Amount</div>
            <div class="text-danger">{{ expense }} mmk</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  income: {
    type: Number,
  },
  expense: {
    type: Number,
  },
});
</script>
