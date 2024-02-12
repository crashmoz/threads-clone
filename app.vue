<template>
  <VitePwaManifest />
  <div class="bg-black fixed w-[calc(100%+1px)] h-full">
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </div>
</template>
<script setup>
const userStore = useUserStore();
</script>