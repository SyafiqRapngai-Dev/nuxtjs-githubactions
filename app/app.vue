<script setup lang="ts">
const textRef = ref('');
const confirmedName = ref('');

function onConfirmName() {
  confirmedName.value = textRef.value;
}
</script>

<template>
  <div class="flex gap-2 m-4 items-center background-fill">
    <label for="text">Insert name here</label>
    <input
      class="border-green-300 focus:border-green-700 border outline-0 p-2"
      v-model="textRef"
      type="text"
      name="text"
    />
    <button
      class="bg-green-700 hover:bg-green-600 transition hover:cursor-pointer border-green-900 text-white p-2 rounded"
      v-on:click="onConfirmName"
    >
      Confirm name
    </button>
  </div>

  <div class="m-4" v-if="confirmedName">
    <h1 class="text-4xl">Hello {{ confirmedName }}!</h1>
  </div>
</template>

<style>
.background-fill {
  background-color: navy;
}
</style>
