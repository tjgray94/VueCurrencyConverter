<script setup>
  import { ref } from 'vue';

  const amount = ref(0);
  const newValue = ref(0);

  const USD2Yen = () => {
    newValue.value = amount.value * 154.53;
  }
</script>

<template>
  <div class="container">
    <h1>Convert US Dollar to Japanese Yen</h1>
    <hr />
    <h6>Enter the amount to convert</h6>

    <label class="form-label">US Dollar: </label>
    <input type="number" class="form-control" v-model="amount" required />
    <hr />
    <button class="btn btn-primary" @click="USD2Yen()">Convert</button>
    <p>{{ newValue }} Yen</p>
  </div>
</template>