<template>
  <main class="container mx-auto">
    <h1 class="p-2 bg-info rounded text-center h3 mt-1">
      <Header :name="name" />
    </h1>
    <div class="container-sm mx-auto p-2 rounded my-2">
      <Balance :totalAmount="totalAmount" />
      <IncomeExpense :income="income" :expense="expense" />
      <TransacationList :transacationLists="transacationLists" />
      <AddTransaction />
    </div>
  </main>
</template>

<script>
import { computed, ref } from "vue";
import AddTransaction from "./components/AddTransaction.vue";
import Balance from "./components/Balance.vue";
import Header from "./components/Header.vue";
import IncomeExpense from "./components/IncomeExpense.vue";
import TransacationList from "./components/TransacationList.vue";

export default {
  name: "App",
  components: {
    Header,
    Balance,
    AddTransaction,
    IncomeExpense,
    TransacationList,
  },
  setup(props) {
    const name = "Money Tracker";

    const transacationLists = ref([
      { id: 1, name: "trasn 1", amount: 200 },
      { id: 2, name: "trasn 2", amount: 1000 },
      { id: 3, name: "trasn 3", amount: -3000 },
      { id: 4, name: "trasn 4", amount: 40000 },
    ]);

    const totalAmount = computed(() => {
      return transacationLists.value.reduce((acc, t) => acc + t.amount, 0);
    });

    const income = computed(() => {
      return transacationLists.value
        .filter((t) => t.amount > 0)
        .reduce((acc, t) => acc + t.amount, 0);
    });

    const expense = computed(() => {
      return transacationLists.value
        .filter((t) => t.amount < 0)
        .reduce((acc, t) => acc + t.amount, 0);
    });

    // console.log(income.value, expense.value);

    return {
      name,
      transacationLists,
      totalAmount,
      income,
      expense,
    };
  },
};
</script>
