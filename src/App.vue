<script setup lang="ts">
import TopNavBar from '@/components/layout/TopNavBar.vue';
import Sidebar from '@/components/layout/Sidebar.vue';
</script>

<template>
  <Sidebar />
  <div class="flex flex-col lg:ml-52 ml-16 transition-[margin]">
    <TopNavBar />
    <main>
      <RouterView />
    </main>
  </div>
</template>
