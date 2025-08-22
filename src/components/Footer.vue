<template>
  <footer
    class="mt-8 border z-10 border-t-[#33353F] border-l-transparent border-r-transparent text-white"
  >
    <div class="container p-12 flex justify-between">
      <p class="text-slate-600">All rights reserved 2025</p>
    </div>
  </footer>
  <button v-if="isVisible" @click="scrollTop"
    class="fixed bottom-4 right-4 bg-gradient-to-r from-[#f59e0b] to-pink-500 text-white rounded-full w-12 h-12 flex items-center justify-center text-xl cursor-pointer transition-opacity duration-300 hover:bg-blue-600"
  >
    ↥
  </button>
</template>

<script setup>
import {ref, onMounted, onUnmounted} from 'vue'
const isVisible = ref(false)
const handleScroll = () => {
  isVisible.value = window.scrollY > 300
}
const scrollTop = () => {
  window.scrollTo({top:0, behavior:'smooth'})
}
onMounted(()=>{
 window.addEventListener('scroll', handleScroll)
})
onUnmounted(()=>{
 window.addEventListener('scroll', handleScroll)
})
</script>

<style scoped>
</style>