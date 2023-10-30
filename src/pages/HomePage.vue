<script setup>
import { reactive, ref } from "vue";

const mockData = [
  { id: 1, name: "Иван", age: 30, email: "ivan@example.com" },
  { id: 2, name: "Мария", age: 28, email: "maria@example.com" },
  { id: 3, name: "Алексей", age: 35, email: "alex@example.com" },
  { id: 4, name: "Елена", age: 32, email: "elena@example.com" },
  { id: 5, name: "Петр", age: 29, email: "petr@example.com" },
  { id: 6, name: "Анна", age: 31, email: "anna@example.com" },
  { id: 7, name: "Сергей", age: 33, email: "sergey@example.com" },
  { id: 8, name: "Ольга", age: 27, email: "olga@example.com" },
  { id: 9, name: "Дмитрий", age: 34, email: "dmitry@example.com" },
  { id: 10, name: "Татьяна", age: 26, email: "tatiana@example.com" },

  { id: 11, name: "Иван", age: 30, email: "ivan@example.com" },
  { id: 12, name: "Мария", age: 28, email: "maria@example.com" },
  { id: 13, name: "Алексей", age: 35, email: "alex@example.com" },
  { id: 14, name: "Елена", age: 32, email: "elena@example.com" },
  { id: 15, name: "Петр", age: 29, email: "petr@example.com" },
  { id: 16, name: "Анна", age: 31, email: "anna@example.com" },
  { id: 17, name: "Сергей", age: 33, email: "sergey@example.com" },
  { id: 18, name: "Ольга", age: 27, email: "olga@example.com" },
  { id: 19, name: "Дмитрий", age: 34, email: "dmitry@example.com" },
  { id: 20, name: "Татьяна", age: 26, email: "tatiana@example.com" },

  { id: 21, name: "Иван", age: 30, email: "ivan@example.com" },
  { id: 22, name: "Мария", age: 28, email: "maria@example.com" },
  { id: 23, name: "Алексей", age: 35, email: "alex@example.com" },
  { id: 24, name: "Елена", age: 32, email: "elena@example.com" },
  { id: 25, name: "Петр", age: 29, email: "petr@example.com" },
  { id: 26, name: "Анна", age: 31, email: "anna@example.com" },
  { id: 27, name: "Сергей", age: 33, email: "sergey@example.com" },
  { id: 28, name: "Ольга", age: 27, email: "olga@example.com" },
  { id: 29, name: "Дмитрий", age: 34, email: "dmitry@example.com" },
  { id: 30, name: "Татьяна", age: 26, email: "tatiana@example.com" },
];

const data = reactive(mockData);
const currentPage = ref(1);

const onChangePage = (page) => {
  currentPage.value = page;
};
</script>

<template>
  <div>
    <MyTable
      :data="data"
      :currentPage="currentPage"
      :onChangePage="onChangePage"
    />
  </div>
</template>

<style scoped></style>
<script>
import MyTable from "@/components/MyTable";
export default {
  components: { MyTable },
};
</script>
