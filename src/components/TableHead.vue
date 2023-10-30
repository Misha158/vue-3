<script setup>
import { defineProps } from "vue";

const props = defineProps({
  columnNames: Array,
  onChangeSortType: Function,
});
</script>

<template>
  <thead>
    <tr
      class="text-md font-semibold tracking-wide text-left text-white bg-gray-800 uppercase border-b border-gray-600"
    >
      <th class="px-4 py-3" v-for="column in props.columnNames" :key="column">
        <div>{{ column.title }}</div>
        <div
          :class="{ activeSortType: column.sortingType === 'asc' }"
          class="text-xs"
          @click="onChangeSortType('asc', column.title)"
        >
          Ask
        </div>
        <div
          :class="{ activeSortType: column.sortingType === 'desc' }"
          class="text-xs"
          @click="onChangeSortType('desc', column.title)"
        >
          Desc
        </div>
      </th>
    </tr>
  </thead>
</template>

<style scoped></style>
