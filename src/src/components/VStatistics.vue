<template>
  <section class="statistic">
    <div class="container">
      <div class="statistic__wrapper">
        <v-statistic-block
          class="statistic__block"
          v-for="s in statistic"
          :statistic-item="s"
          :key="s.id"
        ></v-statistic-block>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import VStatisticBlock from "./VStatisticBlock.vue";

const statistic = [
  {
    id: 1,
    info: "1000",
    symbol: "+",
    title: "Довольных пользователей",
  },
  {
    id: 2,
    info: "85",
    symbol: "%",
    title: "Точность прогнозов",
  },
  {
    id: 3,
    info: "100",
    symbol: "+",
    title: "Подключенных ВУЗов",
  },
];
</script>

<style scoped lang="scss">
.statistic {
  padding: 50px 0;
  background-color: #2563eb;

  // .statistic__wrapper

  &__wrapper {
    display: flex;
    justify-content: center;
    gap: 150px;
    flex-wrap: wrap;
  }

  // .statistic__block

  &__block {
  }
}
</style>
