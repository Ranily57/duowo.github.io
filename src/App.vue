<script setup>
import SimpleText from './components/SimpleText.vue';
import { useDark, useToggle } from '@vueuse/core';
import logoDark from "./assets/img/logo_dark.png";
import logoWhite from "./assets/img/logo_white.png"

const isDark = useDark();
const toggleDark = useToggle(isDark);

var themeDark = "hidden dark:visible dark:flex dark:justify-center dark:items-center dark:me-12";
var themeLight = "dark:hidden visible flex justify-center items-center me-12";
</script>

<template>
  <div class="flex items-center justify-center h-screen">
    <header>
      <div @click="toggleDark()" :class="[ isDark ? themeDark : themeLight ]">
          <img data-tooltip-target="tooltip-logo" alt="DW Logo" class="logo" :src="[ isDark ? logoDark : logoWhite ]" width="125" height="125" draggable="false" />
      </div>
      <div id="tooltip-logo" role="tooltip" class="absolute z-10 invisible inline-block px-3 py-2 text-sm font-medium transition-opacity duration-300 rounded-lg shadow-sm opacity-0 tooltip">
        {{ isDark ? "Click for Switch to Light" : "Click for Switch to Dark" }}
          <div class="tooltip-arrow" data-popper-arrow></div>
      </div>
    </header>
    <main>
      <div class="text-center">
        {{ isDark ? "Dark" : "Light" }}
      </div>
      <SimpleText 
        name="D U O W O" 
        first="Ranily"
        firstGH="https://github.com/Ranily57"
        second="Ashrilys"
        secondGH="https://github.com/Ashrilys"  
      />
    </main>
  </div>
  
</template>

<style scoped>

</style>
