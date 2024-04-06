<template>

</template>

<script setup>
import { useArticles } from '@/composables/useArticles';

const limit = 4
const articles = useArticles()
const topRecentArticles = articles.value?.slice(0, limit)
</script>

<style scoped>
.posts-list {
  display: flex;
  flex-flow: row wrap;
  gap: 1rem;
  width: min(160ch, 100% - 2rem);

  & #posts-heading {
    text-transform: uppercase;
    flex-basis: 100%;
  }
}
</style>
