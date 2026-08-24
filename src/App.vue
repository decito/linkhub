<script setup lang="ts">
import AppFooter from '@/components/AppFooter.vue'
import AppHeader from '@/components/AppHeader.vue'
import InfoDiv from '@/components/InfoDiv.vue'
import { useColorMode } from '@vueuse/core'
import { RouterView } from 'vue-router'

const mode = useColorMode()
mode.value = 'auto'
</script>

<template>
  <main class="mx-auto flex h-screen max-w-2xl flex-col items-center justify-between px-2 sm:px-4">
    <AppHeader />
    <RouterView />
    <AppFooter />
    <InfoDiv />
  </main>
</template>
