<script setup lang="ts">
import { ref } from "vue"
const value1 = ref("");
const value2 = ref("");

const handleBlurValue1 = ((e: Event) => {
  const target = e.target as HTMLInputElement;
  value1.value = value1.value.toUpperCase();
  // value1.value && alert(`[handleBlurValue1]: ${target}`)
})

const handleBlurValue2 = (() => {
  value2.value = value2.value.toUpperCase();
})

const handleTouchStart = ((event: Event) => {
  const target = event.target as HTMLInputElement;
  target.focus()
})

</script>

<template>
  {{ `更新回数: ${8}回目` }}
  <main>
    <div>
      <label>value1:</label>
      <input v-model="value1" type="text" maxlength="11" :tabindex="1" @blur="handleBlurValue1"
        @touchstart="handleTouchStart" />
    </div>
    <div>
      <label>valueX:</label>
      <input type="text" readonly :tabindex="-1" />
    </div>
    <div>
      <label>value2:</label>
      <input v-model="value2" type="text" :tabindex="1" @blur="handleBlurValue2" @touchstart="handleTouchStart" />
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