<script setup lang="ts">
import { useMouse } from '@vueuse/core'

const { x, y } = useMouse()
const color = useColorMode()

function toggleColorMode() {
  color.value = color.value === 'dark' ? 'light' : 'dark'
}
</script>

<template>
  <div class="text-red">
    Hello World {{ x }}, {{ y }} <br>
    <client-only>
      <button @click="toggleColorMode">
        {{ color.value }}
      </button>
    </client-only>
  </div>
</template>
