<script setup lang='ts'>
import { defineAsyncComponent, ref } from 'vue'
import { HoverButton, SvgIcon, UserAvatar } from '@/components/common'

const Setting = defineAsyncComponent(() => import('@/components/common/Setting/index.vue'))

const show = ref(false)
</script>

<template>

  <footer class="flex items-center justify-between min-w-0 p-2 overflow-hidden border-t dark:border-neutral-800">
    <div class="flex-1 flex-shrink-0 overflow-hidden">
        <a href="https://www.dsyydh.com" target="_blank" alt="电商运营导航">
                <img src="http://124.223.186.89:211/wp-content/uploads/2023/04/kongque.jpg" alt="这个空缺">
                </a>
    </div>
    <Setting v-if="show" v-model:visible="show" />
  </footer>

  <footer class="flex items-center justify-between min-w-0 p-4 overflow-hidden border-t dark:border-neutral-800">
    <div class="flex-1 flex-shrink-0 overflow-hidden">
      <UserAvatar />
    </div>

    <HoverButton @click="show = true">
      <span class="text-xl text-[#4f555e] dark:text-white">
        <SvgIcon icon="ri:settings-4-line" />
      </span>
    </HoverButton>

    <Setting v-if="show" v-model:visible="show" />
  </footer>
</template>
