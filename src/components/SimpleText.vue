<script setup>
defineProps({
  name: {
    type: String,
    required: true
  },
  firstGH: {
    type: String,
    required: true
  },
  first: {
    type: String,
    required: true
  },
  secondGH: {
    type: String,
    required: true
  },
  second: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="text-center">
    <h1 class="dark:text-slate-200 text-5xl">{{ name }}</h1>
    <h3 class="text-2xl">
      <a data-tooltip-target="tooltip-github" data-tooltip-placement="bottom" :href="firstGH" target="_blank" title="View the GitHub Profile" rel="noopener">
        {{ first }}
      </a> +
      <a data-tooltip-target="tooltip-github" data-tooltip-placement="bottom" :href="secondGH" target="_blank" title="View the GitHub Profile" rel="noopener">
        {{ second }}
      </a>
    </h3>
    <div id="tooltip-github" role="tooltip" class="absolute z-10 invisible inline-block px-3 py-2 text-sm font-medium rounded-lg shadow-sm opacity-0 tooltip transition-opacity duration-300">
      View the GitHub Profile
      <div class="tooltip-arrow" data-popper-arrow></div>
    </div>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
}

h3 {
  font-size: 1.2rem;
}
</style>
