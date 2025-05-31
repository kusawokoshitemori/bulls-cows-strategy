<template>
  <div class="game-container">Game</div>
  <NumberInput />
</template>

<script setup lang="ts">
import NumberInput from "./NumberInput.vue";
</script>

<style scoped>
.game-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 80vh; /* 画面の縦中央に配置 */
  font-size: 2rem;
  font-weight: bold;
}
</style>
