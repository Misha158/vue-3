<script setup>
import { defineProps } from "vue";

const props = defineProps({
  data: Array,
});
</script>

<template>
  <tbody class="bg-white divide-y divide-gray-200 bo">
    <tr
      class="text-gray-700 hover:bg-gray-100"
      v-for="record in props.data"
      :key="record.id"
    >
      <td class="px-4 py-3">{{ record.id }}</td>
      <td class="px-4 py-3">{{ record.name }}</td>
      <td class="px-4 py-3">{{ record.age }}</td>
      <td class="px-4 py-3">{{ record.email }}</td>
    </tr>
  </tbody>
</template>

<style scoped></style>
