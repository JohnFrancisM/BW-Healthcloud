<template>
  <div>
    <header class="shadow-sm bg-white">
      <nav class="container mx-auto p-4 flex justify-between">
        <NuxtLink to="/" class="font-bold">DNPM : DIP</NuxtLink>
        <ul class="flex gap-4">
          <li><NuxtLink to="/" class="btn">Home</NuxtLink></li>
          <li><NuxtLink to="/search" class="btn">RD</NuxtLink></li>
          <li><NuxtLink to="/list" class="btn">MTB</NuxtLink></li>
        </ul>
      </nav>
    </header>
    <div class="container mx-auto p-4">
      <slot />
    </div>
  </div>
</template>

<style scoped>
  .router-link-exact-active {
    color: #3730a3;
  }
</style>