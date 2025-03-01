<template>
  <v-app-bar color="#fff" class="header">
    <v-app-bar-title class="header__navigation">
      <v-btn class="header__btn">
        <v-icon class="header__icon" icon="mdi-login"></v-icon>
        Войти
      </v-btn>
      <v-btn class="header__btn">
        <v-icon class="header__icon" icon="mdi-account"></v-icon>
        Регистрация
      </v-btn>
    </v-app-bar-title>
  </v-app-bar>
  <HeroSection />
  <Why-We />
  <v-statistics />
  <v-callback />
</template>

<script lang="ts" setup>
import HeroSection from "@/components/HeroSection.vue";
import WhyWe from "@/components/WhyWe.vue";
import VStatistics from "@/components/VStatistics.vue";
import VCallback from "@/components/VCallback.vue";
</script>

<style lang="scss">
.header {
  &__navigation {
    display: flex;
    justify-content: end;
  }
  &__icon {
    margin-right: 5px;
  }
}
.container {
  margin: 0 auto;
  max-width: 1450px;
}
</style>
