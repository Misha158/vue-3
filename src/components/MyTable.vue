<script setup>
import TableHead from "@/components/TableHead";
import TableBody from "@/components/TableBody";
import { defineProps, computed } from "vue";
import MyPagination from "@/components/MyPagination";

const props = defineProps({
  data: Array,
  currentPage: Number,
  onChangePage: Function,
});

const paginationData = computed(() => {
  console.log(
    "props.data.slice(5 * props.currentPage, 5);",
    props.data.slice(0, 5)
  );
  const pageSize = 5;
  return props.data.slice(
    pageSize * (props.currentPage - 1),
    props.currentPage * pageSize
  );
});
</script>

<template>
  <div class="container mx-auto p-6">
    <div class="w-full overflow-hidden rounded-lg shadow-xs">
      <div class="w-full overflow-x-auto">
        <table class="w-full whitespace-nowrap">
          <TableHead />
          <TableBody :data="paginationData" />
        </table>
        <MyPagination
          :currentPage="props.currentPage"
          :totalPages="data.length / 5"
          :onChangePage="props.onChangePage"
        />
      </div>
    </div>
  </div>
</template>

<style>
table {
  border-collapse: collapse;
  width: 100%;
}

th,
td {
  text-align: left;
  padding: 12px;
}

tr:nth-of-type(even) {
  background-color: #f9fafb;
}
</style>
