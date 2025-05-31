<template>
  <form @submit.prevent="submitGuess">
    <input
      v-model="guess"
      maxlength="3"
      pattern="\d{3}"
      placeholder="3桁の数字"
    />
    <button type="submit">送信</button>
  </form>
</template>

<script setup lang="ts">
import { ref } from "vue";

// guessの型をstringにする
const guess = ref<string>("");

// 親コンポーネントに値を渡すためのemit
const emit = defineEmits<{
  (e: "guess", value: string): void;
}>();

function submitGuess() {
  if (/^\d{3}$/.test(guess.value) && new Set(guess.value).size === 3) {
    emit("guess", guess.value);
    guess.value = "";
  } else {
    alert("3桁の重複しない数字を入力してください");
  }
}
</script>
