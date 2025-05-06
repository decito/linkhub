<script setup lang="ts">
import CardItem from '@/components/CardItem.vue'
import { items } from '@/storage'
import { ref } from 'vue'

const list = ref(items.sort((a, b) => a.order - b.order))
</script>

<template>
  <section class="mx-auto flex w-full flex-col gap-4">
    <CardItem v-for="item in list" :key="item.name" :item="item" />
  </section>
</template>
