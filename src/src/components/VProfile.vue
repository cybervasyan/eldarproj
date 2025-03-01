<template>
  <section class="profile">
    <div class="wrapper">
      <h2>Личные данные</h2>
      <div class="profile__content">
        <div class="email">
          <h5>Электронная почта</h5>
          <div v-if="!isChangeEmail">
            <button>
              <span class="email__title">{{ email }}</span>
              <span
                class="mdi mdi-pencil"
                @click="isChangeEmail = !isChangeEmail"
              ></span>
            </button>
          </div>
          <div class="email__input" v-else>
            <input
              class="input-email"
              typa="email"
              placeholder="example@mail.ru"
              v-model="email"
            />
            <button>
              <span class="mdi mdi-check"></span>
            </button>
          </div>
        </div>
        <div class="reg-date">
          <h5>Дата регистрации</h5>
          <span>{{ regDate }}</span>
        </div>
      </div>
      <div class="profile__settings">
        <v-btn :color="'#fff'">Изменить пароль</v-btn>
        <v-btn :color="'#fff'" disabled>Настройки уведомлений</v-btn>
      </div>
    </div>
  </section>
</template>
<script setup lang="ts">
import { ref } from "vue";
const isChangeEmail = ref(false);
const email = ref("2s1eC@example.com");
const regDate = ref("01.01.2023");
</script>

<style lang="scss" scoped>
.profile {
  &__content {
    margin-top: 50px;
    display: flex;
    gap: 55px;
    margin-bottom: 30px;
    h5 {
      margin-bottom: 5px;
    }
  }
  &__settings {
    display: flex;
    gap: 55px;
  }
}

.email {
  &__title {
    margin-right: 6px;
  }
  &__input {
    display: flex;
    align-items: center;
    gap: 15px;
    button {
      .mdi {
        font-size: 24px;
      }
    }
  }
  .mdi {
    border: 1px solid #fff;
    padding: 2px 4px;
    border-radius: 2px;
    transition: 0.5s;
  }
  .mdi:hover {
    cursor: pointer;
    background-color: #fff;
    color: #000;
  }
}

.input-email {
  border: 1px solid #fff;
  border-radius: 2px;
  width: 200px;
  padding: 5px;
  font-size: 16px;
  &:focus {
    outline: none;
  }
  &::placeholder {
    font-size: 13px;
  }
}
</style>
