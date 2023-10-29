<script setup>
import TableHead from "@/components/TableHead";
import TableBody from "@/components/TableBody";
import { defineProps, ref } from "vue";
import MyPagination from "@/components/MyPagination";

const props = defineProps({
  data: Array,
});

const currentPage = ref(1);

const onChangePage = (page) => {
  console.log("page", page);
  currentPage.value = page;
};
</script>

<template>
  <div class="container mx-auto p-6">
    <div class="w-full overflow-hidden rounded-lg shadow-xs">
      <div class="w-full overflow-x-auto">
        <table class="w-full whitespace-nowrap">
          <TableHead />
          <TableBody :data="props.data" />
        </table>
        <MyPagination
          :currentPage="currentPage"
          :totalPages="6"
          :onChangePage="onChangePage"
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
