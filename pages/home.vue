<script setup lang="ts">
import { useI18n } from 'vue-i18n'

definePageMeta({
  middleware: 'auth',
  alias: ['/signin/callback'],
})

const { t } = useI18n()
useHeadFixed({
  title: () => t('nav.home'),
})
</script>

<template>
  <MainContent>
    <template #title>
      <NuxtLink to="/home" timeline-title-style flex items-center gap-2 @click="$scrollToTop">
        <div i-ri:home-5-line />
        <span>{{ $t('nav.home') }}</span>
      </NuxtLink>
    </template>

    <TimelineHome v-if="isMastoInitialised" />
  </MainContent>
</template>
