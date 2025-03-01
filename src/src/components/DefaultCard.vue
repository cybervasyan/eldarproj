<template>
  <div class="card">
    <div class="card__icon">
      <v-icon :icon="icon"></v-icon>
    </div>
    <div class="card__title">
      <h4>{{ title }}</h4>
    </div>
    <div class="card__description">
      <p>
        {{ description }}
      </p>
    </div>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";
interface Iprops {
  title: string;
  description: string;
  icon: string;
}

const props = defineProps<Iprops>();

console.log(props.title, props.description);
</script>

<style lang="scss" scoped>
.card {
  max-width: 280px;
  padding: 15px;
  color: #000000;
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 8px;
  &:hover {
    transition: 0.3s;
    box-shadow: 3px 3px 10px -5px #2563eb;
    border-color: #2563eb;
    .card__icon {
      border-color: #2564ebbd;
    }
  }
  &__icon {
    margin-bottom: 10px;
    font-size: 30px;
    color: #2563eb;
    border: 1px solid #2564eb31;
    border-radius: 4px;
    display: inline-block;
    padding: 5px;
    transition: 0.5s;
  }
  &__title {
    font-size: 18px;
    margin-bottom: 5px;
    color: #353535;
  }
  &__desciption {
  }
}
</style>
