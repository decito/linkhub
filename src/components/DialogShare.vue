<script setup lang="ts">
import { copyToClipboard } from '@/helpers'
import { shareLink, socials } from '@/storage/socials'

defineProps({ open: Boolean })
defineEmits(['closeModal'])
</script>

<template>
  <div
    :class="[
      open ? 'fixed' : 'hidden',
      'bg-background/80 inset-0 z-40 flex items-center justify-center'
    ]"
  >
    <div class="bg-background flex w-[520px] flex-col items-center space-y-6 rounded-lg">
      <div class="relative flex w-full justify-center">
        <h3 class="pt-4 font-medium">Compartilhar o perfil</h3>
        <button
          class="absolute top-3 right-3 flex w-4 items-center justify-center"
          @click="$emit('closeModal')"
        >
          <i class="fas fa-xmark" />
        </button>
      </div>
      <div class="flex w-full justify-center gap-4 px-4">
        <input
          type="text"
          class="border-button-hover bg-background rounded border-2 px-2 py-1 font-medium"
          :value="shareLink"
          @click="copyToClipboard"
          readonly
        />
        <button type="button" @click="copyToClipboard">
          <i class="far fa-copy" />
        </button>
      </div>
      <div class="flex w-full justify-center gap-8 px-4 pb-6">
        <div v-for="social in socials" :key="social.name">
          <a :href="social.link" target="_blank" class="flex flex-col items-center space-y-2">
            <div
              :class="`p-4', flex size-12 items-center justify-center rounded-full card-${social.type} bg-${social.type === 'instagram' ? 'instagram-gradient' : social.type}`"
            >
              <i :class="[social.icon, 'text-2xl text-white']" />
            </div>
            <p class="text-xs">{{ social.name }}</p>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>
