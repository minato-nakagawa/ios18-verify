<script setup lang="ts">
import { ref } from "vue"
const value1 = ref("");
const value2 = ref("");

const handleBlurValue1 = (() => {
  value1.value = value1.value.toUpperCase();
})

const handleBlurValue2 = (() => {
  value2.value = value2.value.toUpperCase();
})

</script>

<template>
  <main>
    <div>
      <label>value1:</label>
      <input v-model="value1" type="text" maxlength="11" :tabindex="1" @blur="handleBlurValue1" />
    </div>
    <div>
      <label>valueX:</label>
      <input type="text" readonly :tabindex="-1" />
    </div>
    <div>
      <label>value2:</label>
      <input v-model="value2" type="text" :tabindex="1" @blur="handleBlurValue2" />
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
  }
}
</style>