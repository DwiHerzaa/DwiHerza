<template>
  
</template>

<script setup>
import { defineAsyncComponent } from 'vue'
import { useContributions } from '@/composables/useContributions';

const GithubRepoCard = defineAsyncComponent({
  loader: () => import('@/components/github/GithubRepoCard.vue'),
  loadingComponent: '<p>Loading...</p>',
})

const pullRequests = useContributions();
</script>

<style scoped>
.github-projects {
  & > :is(h3, h4) {
    flex-basis: 100%;
    text-transform: uppercase;
  }

  & h4 {
    color: var(--color-gray-400);
    font-size: var(--text-sm);
    margin: 10px 0 15px 0;
  }
}

.github-projects,
.github-repositories {
  flex-wrap: wrap;
}

.github-repositories {
  --github-card-size: 270px;
  display: grid;
  grid-gap: 1rem;
  grid-template-columns: repeat(auto-fill, minmax(var(--github-card-size), 1fr));
  width: 100%;
}

</style>
