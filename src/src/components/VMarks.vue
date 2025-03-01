<template>
  <section class="marks">
    <div class="wrapper">
      <h2>Ввод баллов ЕГЭ</h2>
      <div class="marks__content">
        <div class="marks__block" :key="mark.id" v-for="mark in marks">
          <v-text-field
            :label="mark.name"
            v-model="mark.mark.value"
            clearable
          ></v-text-field>
        </div>

        <div
          class="marks__block marks__add"
          @click="isFormVisible = true"
          v-show="!isFormVisible"
        >
          <span class="mdi mdi-plus"></span>
        </div>
      </div>
      <div class="marks__form" v-if="isFormVisible">
        <div class="marks__form-title">
          <h2>Заполните данные о предмете</h2>
        </div>
        <div class="marks__form-block">
          <v-text-field
            label="Введите название предмета"
            v-model="subjectTitle"
            clearable
          ></v-text-field>
        </div>
        <div class="marks__form-block">
          <v-text-field
            v-model="subjectMark"
            label="Введите кол-во баллов"
            clearable
          ></v-text-field>
        </div>
        <div class="marks__form-block" @click="addSubject">
          <v-btn size="large" color="#fff"> Добавить </v-btn>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { computed, ref } from "vue";

const isFormVisible = ref(false);

const subjectTitle = ref("");
const subjectMark = ref(0);

const marks = computed(() => [
  {
    id: 1,
    name: "Математика",
    mark: ref(85),
  },
  {
    id: 2,
    name: "Русский язык",
    mark: ref(0),
  },
  {
    id: 3,
    name: "Физика",
    mark: ref(0),
  },
]);

function addSubject() {
  marks.value.push({
    id: marks.value.length + 1,
    name: subjectTitle.value,
    mark: ref(subjectMark.value),
  });
  isFormVisible.value = false;
}
</script>

<style scoped lang="scss">
.marks {
  &__content {
    margin-top: 50px;
    display: flex;
    gap: 25px;
  }
  &__block {
    width: 300px;
  }
  &__form {
    margin-top: 70px;
    padding-top: 40px;
    border-top: 1px solid #ffffff65;
  }
  &__form-title {
    margin-bottom: 20px;
  }
  &__form-block {
    width: 500px;
  }
  &__add {
    width: 56px;
    height: 56px;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 1px solid #ffffff65;
    font-size: 50px;
    transition: 0.5s;
    cursor: pointer;
    & > span {
      transition: 0.5s;
    }
    &:hover {
      border: 1px solid #ffffffaf;
      & > span {
        transition: 0.5s;
        transform: rotate(15deg);
      }
    }
  }
}
</style>
