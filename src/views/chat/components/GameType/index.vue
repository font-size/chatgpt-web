<script setup lang='ts'>
import { NAlert, NButton } from 'naive-ui'
import { SvgIcon } from '@/components/common'

interface Props {
  title?: string
  desc?: string
  icon?: string
  type?: string
}

interface Emit {
  (ev: 'selectGameType', params: string): void
}

const props = defineProps<Props>()

const emit = defineEmits<Emit>()

function beginGame() {
  emit('selectGameType', props.type || '')
}
</script>

<template>
  <div class="relative w-full mb-6 mt-6 overflow-hidden">
     <NAlert :title="title" :type="type === 'humanGuess' ? 'success' : 'info'">
      <template #icon>
         <SvgIcon :icon="icon" />
      </template>
      <div class="flex justify-between">
     <div class="w-3/4">
      {{ desc }}
     </div>
      <div class="absolute right-2.5" style="top: 50%;transform: translateY(-50%); ">
        <NButton type="success"  @click="beginGame">
            开始游戏
        </NButton>
        </div>
      </div>
    </NAlert>
  </div>
</template>
