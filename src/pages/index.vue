<script setup lang="ts">
const user = useUserStore()
const name = $ref(user.savedName)

const router = useRouter()
const go = (path: string) => {
  router.push(`/${path}`)
}

const { t } = useI18n()
const pages = [
  {
    name: '001',
    path: '001',
  },
]
</script>

<template>
  <div>
    <div v-for="item, idx in pages" :key="idx" @click="go(item.path)">
      {{ item.name }}
    </div>
  </div>
</template>

<route lang="yaml">
meta:
  layout: home
</route>
