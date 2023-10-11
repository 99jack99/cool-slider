<script setup>
import { authors } from "./helpers/fake_api";

console.log(authors);
</script>

<template>
  <div class="wall">
    <h1 class="wall__title">Warriors of 20's century</h1>
    <div class="wall__box">
      <div
        class="wall__box__card"
        v-for="aut in authors"
        :key="aut.id"
        :style="{ backgroundImage: aut.img }"
      >
        <div class="wall__box__card__info">
          <h1>{{ aut.name }}</h1>
          <h3>{{ aut.motto }}</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.wall {
  /* background-color: lightgrey; */
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100vh;
  width: 100vw;

  &__title {
    color: azure;
    display: flex;
    justify-content: center;
    font-size: 5em;
  }

  &__box {
    /* background-color: black; */
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 20px;

    &__card {
      background-size: cover;
      background-position: top;
      filter: grayscale(1);

      width: 200px;
      height: 400px;
      margin-inline: 5px;
      border-radius: 20px;

      transition: 1s ease-in-out;

      &__info {
        margin-left: 30px;
        display: none;
      }

      &:hover {
        width: 400px;
      }

      &:hover &__info {
        display: block;
      }
    }
  }
}
</style>
