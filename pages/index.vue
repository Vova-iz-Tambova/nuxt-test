<script setup>
// import { useFetch } from 'nuxt/app'

const { data } = await useFetch('http://localhost:3002/posts')
</script>

<template>
  <div v-if="isLoading">Loading...</div>
  <div v-else-if="!data.length">Posts not found</div>

  <ul v-else>
    <li :key="post.id" v-for="post in data">
      <span>{{ post.id }} - {{ post.title }}</span>
      <!-- <button :disabled="isLoadingDelete" @click="mutate(post.id)">X</button> -->
    </li>
  </ul>
</template>
