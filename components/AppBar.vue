<script lang="ts" setup>
const user = useSupabaseUser();
const handleLogout = async () => {
  const { auth } = useSupabaseAuthClient();
  try {
    await auth.signOut();
    navigateTo("/");
  } catch (error) {
    console.log(error);
  }
};
</script>

<template>
  <div
    class="fixed top-0 left-0 right-0 border-b border-white/20 bg-white/10 backdrop-filter backdrop-blur-lg z-50"
  >
    <nav class="container mx-auto py-4 flex justify-between items-center">
      <NuxtLink class="font-bold font-heading flex justify-between items-center" to="/">
          <img class="h-9" src="../assets/images/logo.png" alt="logo">
        <h2 class="text-2xl font-bold ml-4 text-white">SNIPPY URL</h2>
      </NuxtLink>
      <!-- <div class="flex justify-center">
      <NuxtLink to="/" class="navbar-brand text-2xl font-bold text-white">
        <img src="../assets/images/logo.png" width="20" height="20" />
        Snippy URL
      </NuxtLink>
    </div> -->
      <ul class="flex items-center">
        <li class="mr-6 text-xs">
          <nuxt-link v-if="user" :to="{ name: 'dashboard' }" class="btn"
            >Dashboard</nuxt-link>
          <nuxt-link
            v-else
            :to="{
              name: 'auth',
            }"
            class="btn"
            >Signin</nuxt-link
          >
        </li>
        <li v-if="user" class="grid place-content-center">
          <button @click="handleLogout">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-6 h-6"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M15.75 9V5.25A2.25 2.25 0 0013.5 3h-6a2.25 2.25 0 00-2.25 2.25v13.5A2.25 2.25 0 007.5 21h6a2.25 2.25 0 002.25-2.25V15M12 9l-3 3m0 0l3 3m-3-3h12.75"
              />
            </svg>
          </button>
        </li>
      </ul>
    </nav>
  </div>
</template>
