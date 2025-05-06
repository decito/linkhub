<script setup lang="ts">
import { ref } from 'vue'
import DialogShare from './DialogShare.vue'

const open = ref(false)
</script>

<template>
  <header class="flex w-full items-center justify-between pt-6">
    <a href="https://github.com/decito/linkhub" target="_blank" class="rounded-full">
      <button
        type="button"
        class="bg-button text-foreground hover:bg-button-hover flex size-12 items-center justify-center gap-4 rounded-full p-4 transition-colors duration-300"
      >
        <i class="fab fa-github fa-xl" />
      </button>
    </a>
    <button
      type="button"
      class="bg-button text-foreground hover:bg-button-hover flex size-12 items-center justify-center rounded-full p-4 transition-colors duration-300"
      @click="open = true"
    >
      <template v-if="false">
        <!-- TODO: verificar como usar o menu de contexto dos dispositivos -->
        <!-- <i class="fas fa-up-right-from-square"></i> -->
      </template>
      <i class="fas fa-arrow-up-from-bracket" />
    </button>
    <Teleport to="#dialog-container">
      <DialogShare v-if="open" :open="open" @close-modal="open = false" />
    </Teleport>
  </header>
</template>
