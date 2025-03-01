<template>
  <section class="hero">
    <div class="container">
      <div class="hero__title">
        <h1>
          Поступай в ВУЗ <br />
          уверенно с AdmitPro
        </h1>
      </div>
      <div class="hero__description">
        <p>
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Numquam,
          nihil<br />
          quia laborum rem optio mollitia veniam suscipit possimus
          dignissimos<br />
          maiores nobis voluptas dolor dolorum sed! Id error, exercitationem
          quae<br />
          expedita et iste atque quidem dicta dolor impedit vel libero ab?
        </p>
      </div>
      <div class="hero__buttons">
        <v-btn size="large" variant="outlined" class="hero_button">
          Начать бесплатно
        </v-btn>
        <v-btn
          size="large"
          color="#ffffff"
          class="hero_button text-blue-darken-2"
        >
          Узнать больше
        </v-btn>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped>
.hero {
  padding: 90px 0 80px 0;
  background: #2563eb;
  &__title {
    display: flex;
    justify-content: center;
    margin-bottom: 35px;
    h1 {
      text-align: center;
      line-height: 50px;
      font-size: 50px;
    }
  }
  &__description {
    text-align: center;
    margin-top: 15px;
    padding: 0 50px;
    P {
      line-height: 30px;
    }
  }
  &__buttons {
    margin-top: 25px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 15px;
  }
  // &_button {
  //   color: #2563eb;
  // }
}
</style>
