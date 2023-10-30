<script setup>
import TableHead from "@/components/TableHead";
import TableBody from "@/components/TableBody";
import { defineProps, computed, ref } from "vue";
import MyPagination from "@/components/MyPagination";

const props = defineProps({
  data: Array,
  currentPage: Number,
  onChangePage: Function,
});

const reactiveData = ref(props.data);

const paginationData = computed(() => {
  const pageSize = 5;
  return reactiveData.value.slice(
    pageSize * (props.currentPage - 1),
    props.currentPage * pageSize
  );
});
const columnNames = ref([
  {
    title: "#",
    sortingType: "asc",
  },
  {
    title: "Name",
    sortingType: "asc",
  },
  {
    title: "Age",
    sortingType: "asc",
  },
  {
    title: "Email",
    sortingType: "asc",
  },
]);

const onChangeSortType = (sortType, columnName) => {
  const columnNameLowerCase = columnName.toLowerCase();

  reactiveData.value = reactiveData.value.slice().sort((a, b) => {
    const nameA = a[columnNameLowerCase];
    const nameB = b[columnNameLowerCase];

    if (sortType === "asc") {
      if (nameA > nameB) {
        return 1;
      }
      if (nameA < nameB) {
        return -1;
      }
    } else if (sortType === "desc") {
      if (nameA < nameB) {
        return 1;
      }
      if (nameA > nameB) {
        return -1;
      }
    }

    return 0;
  });

  columnNames.value = columnNames.value.map((column) => {
    if (column.title === columnName) {
      return { ...column, sortingType: sortType };
    }

    return column;
  });
};
</script>

<template>
  <div class="container mx-auto p-6">
    <div class="w-full overflow-hidden rounded-lg shadow-xs">
      <div class="w-full overflow-x-auto">
        <table class="w-full whitespace-nowrap">
          <TableHead
            :columnNames="columnNames"
            :onChangeSortType="onChangeSortType"
          />
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
