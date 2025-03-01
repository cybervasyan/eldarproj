<template>
  <div class="block-statistic">
    <div
      class="block-statistic__info"
      v-counter="[statisticItem.info, statisticItem.symbol]"
    >
      0
    </div>
    <div class="block-statistic__title">
      {{ statisticItem.title }}
    </div>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

interface IProps {
  statisticItem: {
    id: number;
    info: string;
    symbol: string;
    title: string;
  };
}

const props = defineProps<IProps>();

const vCounter = {
  mounted: (el: HTMLElement, binding: any) => {
    const options = {
      root: el.parentNode,
      rootMargin: "100px",
      threshold: 1.0,
    };
    const observer = new IntersectionObserver((entries: any, observer: any) => {
      entries.forEach((entry: any) => {
        if (entry.isIntersecting) {
          console.log("INTERSECT");
          animateValue(el, 0, binding.value[0], binding.value[1]);
        }
      });
    }, options);
    observer.observe(el);
  },
};

function animateValue(
  obj: HTMLElement,
  start = 0,
  end: number,
  symbol?: string,
  duration = 5000
) {
  let startTimestamp: any = null;
  const step = (timestamp: any) => {
    if (!startTimestamp) startTimestamp = timestamp;
    const progress = Math.min((timestamp - startTimestamp) / duration, 1);
    obj.innerHTML = String(Math.floor(progress * (end - start) + start));
    obj.innerHTML += symbol;
    if (progress < 1) {
      window.requestAnimationFrame(step);
    }
  };
  window.requestAnimationFrame(step);
}
</script>

<style lang="scss" scoped>
.block-statistic {
  // .block-statistic__info
  text-align: center;
  &__info {
    font-size: 45px;
    font-weight: 800;
  }

  // .block-statistic__title

  &__title {
    font-weight: 400;
  }
}
</style>
