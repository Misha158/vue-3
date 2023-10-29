<script setup>
const columnNames = ["#", "Имя", "Возраст", "Email"];
</script>

<template>
  <thead>
    <tr
      class="text-md font-semibold tracking-wide text-left text-white bg-gray-800 uppercase border-b border-gray-600"
    >
      <th class="px-4 py-3" v-for="column in columnNames" :key="column">
        {{ column }}
      </th>
    </tr>
  </thead>
</template>

<style scoped></style>
