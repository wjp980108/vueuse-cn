<script setup lang="ts">
import { computed, ref } from 'vue'
import { useFavicon } from '@vueuse/core'

const type = ref('vueuse')

const favicon = computed(() =>
  type.value === 'vue' ? 'vue.png' : 'favicon-32x32.png')

useFavicon(favicon, {
  baseUrl: '/',
  rel: 'icon',
})
</script>

<template>
  <div>
    更改 favicon
  </div>
  <button @click="type = 'vue'">
    Vue
  </button>
  <button @click="type = 'vueuse'">
    VueUse
  </button>
</template>
