<template>
  <section>
    <div class="container">
      <div class="my-2">
        <h4>Add Transaction</h4>
        <form>
          <div class="row">
            <div class="col-6">
              <input
                type="text"
                placeholder="name"
                class="form-control"
                v-model="addTransaction.name"
              />
            </div>
            <div class="col-6">
              <input
                type="number"
                placeholder="amount"
                class="form-control"
                v-model="addTransaction.amount"
              />
            </div>
          </div>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup>
import { reactive } from "vue";

const addTransaction = reactive({
  name: null,
  amount: null,
});

console.log(addTransaction.name, addTransaction.amount);
</script>
