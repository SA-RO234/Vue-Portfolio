<template>
  <header
    class="flex justify-between items-center p-6 bg-opacity-80 relative z-20"
  >
    <div class="text-white text-3xl font-bold">LOGO</div>
    <!-- mobile toggle button  -->
    <div class="md:hidden z-30">
      <button
        type="button"
        class="block focus:outline-none "
        @click="isMenuopen = !isMenuopen"
      >
        <span class="text-5xl" v-if="isMenuopen">
           <img src="https://img.icons8.com/ios-filled/100/ffffff/delete-sign.png" width="50" height="50" alt="Close" >
        </span>
        <span class="text-5xl" v-else>
          <img
            src="https://img.icons8.com/ios-filled/100/ffffff/menu--v6.png"
            alt="Menu"
            width="50"
            height="50"
          />
        </span>
      </button>
    </div>
    <!--  Navbar link -->
    <nav
      :class="[
        'fixed inset-0 z-20 flex flex-col items-center justify-center bg-[#111827] md:relative md:bg-transparent md:flex md:justify-between md:flex-row',
        isMenuopen ? 'block' : 'hidden',
      ]"
    >
      <ul
        class="flex flex-col items-center space-y-5 md:flex-row md:space-x-5 md:space-y-0"
      >
        <li v-for="item in menu" :key="item.name">
          <a
            :href="item.href"
            class="block text-white transition hover:text-primary ease-linear text-2xl md:text-lg"
            @click="Scrolltosection(item.href)"
            >{{ item.name }}</a
          >
        </li>
      </ul>
    </nav>
  </header>
</template>

<script setup>
import { fas } from "@fortawesome/free-solid-svg-icons";
import { ref } from "vue";

const menu = ref([
  { name: "Service", href: "#service" },
  { name: "About me", href: "#aboutme" },
  { name: "Skills ", href: "#skills" },
  { name: "Projects", href: "#projects" },
  { name: "Testimontials", href: "#testimontials" },
  { name: "Contact", href: "#contact" },
]);
const isMenuopen = ref(false);
const Scrolltosection = (href) => {
  isMenuopen.value = false;
  const section = document.querySelector(href);
  if (section) {
    section.scrollIntoView({
      behavior: "smooth",
    });
  }
};
</script>
