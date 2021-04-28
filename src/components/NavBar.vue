<template>
  <nav class="bg-white">
    <div class="container flex items-center justify-between mx-auto">
      <div class="flex items-center space-x-4">
        <noto:film-projector class="w-16 h-16" />
        <p
          class="text-4xl tracking-wider text-transparent bg-gradient-to-r from-red-900 via-red-500 to-red-500 bg-clip-text"
        >
          Movies<span class="font-bold text-blue-900">DB</span>
        </p>
      </div>
      <div>
        <div v-if="isAuthenticated" class="flex items-center space-x-4">
          <p class="text-Blue-900 font-bold">Welcome {{ user?.displayName }}</p>
          <button
            @click="out"
            class="px-8 py-2 font-semibold bg-red-600 rounded focus:ring-red-900 focus:ring-4 focus:outline-none text-coolGray-100 hover:bg-red-800"
          >
            Logout
          </button>
        </div>
        <div v-else>
          <button
            @click="signIn"
            class="px-8 py-2 font-semibold bg-blue-600 rounded focus:ring-blue-900 focus:ring-4 focus:outline-none text-coolGray-100 hover:bg-blue-800"
          >
            Login
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { authentication } from "~/helpers/useFirebase";
import { movies, page } from "~/helpers/useMovies";

const { signIn, signOut, isAuthenticated, user } = authentication();

const out = () => {
  signOut();
  page.value = 1;
  movies.value = [];
};
</script>
