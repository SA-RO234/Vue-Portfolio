<template>
  <button v-if="isvisible" @click="onScrollTotop"
    class="fixed bottom-4 right-4 bg-gradient-to-r from-primary to-pink-500 text-white rounded-full w-12 h-12 flex items-center justify-center text-xl cursor-pointer transition-opacity duration-300 hover:bg-blue-600"
  >
    <font-awesome-icon :icon="['fas', 'arrow-up']" />
  </button>
</template>
<script setup>
import { library } from "@fortawesome/fontawesome-svg-core";
import { faArrowUp} from "@fortawesome/free-solid-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { onMounted, onUnmounted, ref } from "vue";
library.add(faArrowUp);

const isvisible = ref(false)
const handlescroll =()=>{
     isvisible.value = window.scrollY > 300
}

const onScrollTotop =()=>{
     window.scrollTo({top: 0,behavior:'smooth'})
}

onMounted(()=>{
    window.addEventListener('scroll', handlescroll);
});

onUnmounted(()=>{
  window.removeEventListener('scroll',handlescroll);
})
</script>
<style></style>
