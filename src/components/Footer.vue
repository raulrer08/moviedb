<template>
  <footer class="bg-white">
    <div
      class="container flex items-center justify-between px-2 py-4 mx-auto space-x-4 space-y-2 text-blue-900"
    >
      <div class="text-xs">
        Favicon made by
        <a
          href="https://www.flaticon.com/authors/prosymbols"
          title="Prosymbols"
          class="text-red-500"
          >Prosymbols</a
        >
        from
        <a
          href="https://www.flaticon.com/"
          title="Flaticon"
          class="text-red-500"
          >www.flaticon.com</a
        >
      </div>
      <img :src="tmdbLogo" alt="TMDB Logo" class="w-12" />
    </div>
  </footer>
</template>

<script setup>
import tmdbLogo from "~/assets/tmdb.svg";
</script>
