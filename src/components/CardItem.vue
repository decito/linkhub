<script setup lang="ts">
import { switchUserAvatarOutlineColor } from '@/helpers'
import type { CardItem } from '@/types'

defineProps<{ item: CardItem }>()
</script>

<template>
  <a
    :href="item.link"
    target="_blank"
    :class="`bg-${item.type === 'instagram' ? 'instagram-gradient' : item.type} mx-auto flex w-full max-w-2xl transform-gpu items-center rounded-full px-8 py-2 text-white transition-transform duration-200 ease-out hover:scale-105`"
    @mouseenter="switchUserAvatarOutlineColor(item.type)"
  >
    <i class="fa-xl" :class="item.icon" />
    <div class="w-full px-6 break-words">
      <h3 class="font-semibold">{{ item.name }}</h3>
      <p class="text-sm font-medium">@{{ item.username }}</p>
    </div>
  </a>
</template>
