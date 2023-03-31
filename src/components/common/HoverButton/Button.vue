<script setup lang='ts'>
// interface Emit {
//   (e: 'click'): void
// }

// const emit = defineEmits<Emit>()

function handleClick() {
  // emit('click')
}
</script>
<template>
  <button @click="handleClick"
    class="flex items-center justify-center w-10 h-10 transition rounded-full hover:bg-neutral-100 dark:hover:bg-[#414755]"
  >
    <slot />
  </button>
</template>
