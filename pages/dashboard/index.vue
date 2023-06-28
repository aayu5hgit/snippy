<script lang="ts" setup>
</script>

<template>
    <section class="pt-28 container mx-auto">
    <h1 class="text-2xl font-bold text-white">Dashboard</h1>
    <!-- <LinkForm @shorten="handleRefresh" />
    <div class="links-wrapper mt-10">
      <LinkCard v-for="link in data" :key="link.id" :link="link"> </LinkCard> -->
    <!-- </div> -->
  </section>

  <section class="container mt-10">
    <LinkForm/>
  </section>
  
  <section class="container mt-10">
    <LinkItem
    v-for="i in 5"
    :key="i"
    :link="{
        shortKey: 'test',
        longUrl: 'https://github.com/aayu5hgit/snippy',
        id: '1'
    }" 
    class="mb-4"
    />
  </section>
</template>

<style>

</style>