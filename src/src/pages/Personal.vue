<template>
  <main>
    <v-navigation-drawer>
      <v-list-item title="Admit Pro" subtitle="Иван Иванов"></v-list-item>
      <v-divider></v-divider>

      <v-list-item
        v-for="link in links"
        :key="link.id"
        :title="link.name"
        @click="block = link.alias"
      ></v-list-item>
    </v-navigation-drawer>
    <component :is="activeBlock"></component>
  </main>
</template>

<script setup lang="ts">
import { computed, ref } from "vue";
import VProfile from "@/components/VProfile.vue";
import VMarks from "@/components/VMarks.vue";
import VUniversities from "@/components/VUniversities.vue";

const block = ref("VProfile");
const activeBlock = computed(
  () =>
    ({
      VProfile,
      VMarks,
      VUniversities,
    }[block.value])
);

const links = [
  {
    name: "Профиль",
    alias: "VProfile",
    id: 1,
  },
  {
    name: "Баллы ЕГЭ",
    alias: "VMarks",
    id: 2,
  },
  {
    name: "Рекоммендованные ВУЗЫ",
    alias: "VUniversities",
    id: 3,
  },
];
</script>

<style lang="scss">
.wrapper {
  padding: 10px 10px 10px 50px;
}
</style>
