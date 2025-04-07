<script setup>
import { ref, reactive } from 'vue'

const color = ref('red')
const background = ref('blue')
const fontSize = ref('10')

const styleObject = reactive({
  border: 'none',
  borderRadius: '6px'
})
</script>

<template>
  <div>
    <button 
      :style="[
        {
          color: color,
          background: background,
          fontSize: fontSize + 'px'
        },
        styleObject
      ]"
    >
      Click Me
    </button>
  </div>
</template>
