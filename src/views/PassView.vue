<script setup lang="ts">
import { ref } from "vue"
</script>

<template>
  {{ `更新回数: ${1}回目` }}
  <main>
    <div>
      <label>password1:</label>
      <input type="password" />
    </div>
    <div>
      <label>password2:</label>
      <input type="password" class="pass2" />
    </div>
  </main>
</template>

<style lang="scss" scoped>
main {
  width: max-content;
  display: flex;
  padding: min(2vw, 2vh);
  flex-direction: column;
  gap: 16px;

  >div {
    label {
      padding-right: 8px;
    }

    input {
      height: 40px;
      border: 1px solid #aaa;
      border-radius: 3px;

      &:read-only {
        background: #dfdfdf;
        border: 1px solid #aaa;
      }
    }

    .pass2 {
      &::-webkit-reveal-button {
        display: none;
      }
    }
  }
}
</style>