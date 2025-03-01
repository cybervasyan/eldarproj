<template>
  <section class="why-we">
    <div class="container">
      <div class="why-we__title">
        <h1>Почему выбирают нас?</h1>
      </div>
      <div class="why-we__advantages advantages">
        <default-card
          v-for="a in advantages"
          :key="a.id"
          :title="a.title"
          :description="a.description"
          :icon="a.icon"
        ></default-card>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import DefaultCard from "./DefaultCard.vue";

const advantages = [
  {
    id: 1,
    icon: "mdi-brain",
    title: "Умный выбор",
    description:
      "ИИ-система анализирует ваши шансы поступления в реальном времени",
  },
  {
    id: 2,
    icon: "mdi-trending-up",
    title: "Точность 85%+",
    description: "Высокая точность прогнозов благодаря продвинутым алгоритмам",
  },
  {
    id: 3,
    icon: "mdi-school",
    title: "Все ВУЗы России",
    description: "Актуальная информация о вступительных баллах и требованиях",
  },
  {
    id: 4,
    icon: "mdi-clock-time-eight-outline",
    title: "Экономия времени",
    description: "Быстрый анализ шансов поступления без долгих расчётов",
  },
];
</script>

<style lang="scss" scoped>
.why-we {
  padding: 90px 0 90px 0;
  background-color: #fff;
  &__title {
    display: flex;
    justify-content: center;
    margin-bottom: 35px;
    h1 {
      color: #353535;
      text-align: center;
      font-size: 35px;
    }
  }
  &__advantages {
  }
}

.advantages {
  display: flex;
  gap: 20px;
  justify-content: center;
}
</style>
