<script setup>
  import { ref } from 'vue';

  const amount = ref(0);
  const newValue = ref(0);

  const Yen2Usd = () => {
    newValue.value = amount.value / 154.53;
  }

  const formatCurrency = (value) => {
  return new Intl.NumberFormat('en-US', {
    style: 'currency',
    currency: 'USD',
  }).format(value);
};
</script>

<template>
  <div class="container">
    <h1>Convert Japanese Yen to US Dollar</h1>
    <hr />
    <h6>Enter the amount to convert</h6>

    <label class="form-label">Japanese Yen:</label>
    <input type="number" class="form-control" v-model="amount" required />
    <hr />
    <button class="btn btn-primary" @click="Yen2Usd()">Convert</button>
    <p>{{ formatCurrency(newValue) }}</p>
  </div>
</template>