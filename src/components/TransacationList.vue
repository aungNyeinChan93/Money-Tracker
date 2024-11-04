<template>
  <section>
    <div class="container-sm">
      <div
        class="my-1 shadow rounded p-1 text-white"
        v-for="t in transacationLists"
        :key="t.id"
        :class="{ 'bg-success': t.amount > 0, 'bg-danger': t.amount < 0 }"
      >
        <div class="d-flex justify-content-between p-2">
          <span>{{ t.name }}</span>
          <span>{{ t.amount }} mmk</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  transacationLists: {
    type: Array,
    required: true,
  },
});
</script>

<style lang="stylus" scoped></style>
