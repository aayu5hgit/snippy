<script lang="ts" setup>
import { Database } from "~~/types/supabase";
defineProps<{
  link: Database["public"]["Tables"]["links"]["Row"];
}>();

const config = useRuntimeConfig();
</script>

<template>
  <div
    class="link card mb-5 flex justify-between gap-5 hover:border-white/30 transition-all duration-200"
  >
    <div class="w-1/2">
      <div class="text-xl">
        <NuxtLink
          :to="{ name: 'dashboard-id', params: { id: link.key } }"
          class="text-[#0cc496be] font-bold"
          >/{{ link.key }}</NuxtLink
        >
      </div>
      <div class="text-white/50 text-xs sm:text-base">
        {{ link.long_url.slice(0, 20) + "..." }}
      </div>
    </div>
    <div class="w-1/2 link-ation flex justify-end">
      <div class="link-stats flex flex-col items-end justify-center">
        <div class="flex items-end">
          <span class="text-white leading-none text-sm sm:text-base">
            {{ link.total_clicks }}
          </span>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-4 h-4 sm:w-6 sm:h-6 ml-2"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M3 13.125C3 12.504 3.504 12 4.125 12h2.25c.621 0 1.125.504 1.125 1.125v6.75C7.5 20.496 6.996 21 6.375 21h-2.25A1.125 1.125 0 013 19.875v-6.75zM9.75 8.625c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125v11.25c0 .621-.504 1.125-1.125 1.125h-2.25a1.125 1.125 0 01-1.125-1.125V8.625zM16.5 4.125c0-.621.504-1.125 1.125-1.125h2.25C20.496 3 21 3.504 21 4.125v15.75c0 .621-.504 1.125-1.125 1.125h-2.25a1.125 1.125 0 01-1.125-1.125V4.125z"
            />
          </svg>
        </div>
        <div class="text-white/50">
          <span class="text-xs sm:text-sm">{{
            link.created_at?.slice(0, 10)
          }}</span>
        </div>
      </div>
      <CopyBtn :data="'https://snippyurl.vercel.app/' + link.key" />
    </div>
  </div>
</template>
