<script setup lang="ts">
import type { NavItem } from '@nuxt/content/dist/runtime/types'

const navigation = inject<Ref<NavItem[]>>('navigation')

const links = [{
  label: '关于',
  icon: 'i-heroicons-book-open',
  to: '/about'
}, {
  label: '博客',
  icon: 'i-heroicons-square-3-stack-3d',
  to: '/blog'
}, {
  label: '书虫',
  icon: 'i-heroicons-rocket-launch',
  to: '/book'
}]
</script>

<template>
  <UHeader :links="links">
    <template #logo>
      <!-- <img src="/img/ran.png" alt="Discover Nuxt 3" /> -->
      <p class="font-bold text-[#50d71e]">Ran ran</p>
    </template>

    <template #right>
      <UColorModeButton />
    </template>

    <template #panel>
      <UNavigationTree :links="mapContentNavigation(navigation)" />
    </template>
  </UHeader>
</template>