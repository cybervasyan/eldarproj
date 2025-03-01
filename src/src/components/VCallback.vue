<template>
  <section class="callback">
    <div class="container">
      <div class="callback__title">
        <h3>Готовы поступить в ВУЗ мечты?</h3>
      </div>

      <div class="callback__button">
        <v-btn size="large" color="#2563eb"> Попробовать бесплатно </v-btn>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped>
.callback {
  padding: 60px 0;
  background-color: #fff;
  display: flex;
  justify-content: center;
  align-content: center;

  // .callback__title

  &__title {
    color: #353535;
    font-size: 38px;
    margin-bottom: 20px;
  }

  // .callback__button

  &__button {
    display: flex;
    justify-content: center;
  }
}
</style>
