<template>

</template>

<script setup>
import { computed, defineProps } from 'vue'

const props = defineProps({
  thumbnail: String,
  title: String,
  description: String,
  tags: String,
  github: String,
})

const titleSlug = props.title.toLowerCase().replaceAll(' ', '')

const titleId = computed(() => `title-${titleSlug}`)
const buttonId = computed(() => `button-${titleSlug}`)
</script>

<style scoped>
.project-card {
  display: flex;
}

.project-thumbnail {
  flex-basis: 50%;
  border-radius: var(--radius-default) 0 0 var(--radius-default);
}

.project-card__image {
  border-radius: inherit;
  object-fit: cover;
  object-position: top center;
  height: 200px;
  min-height: 100%;
  &.lozad {
    filter: blur(0);
  }
}

.project-card__content {
  display: flex;
  flex-flow: column;
  justify-content: space-between;
  flex-basis: 50%;
  background-color: var(--bg-color-lighter, var(--color-gray-800));
  padding: 1.125rem;
  border-radius: 0 var(--radius-default) var(--radius-default) 0;
  border: 1px solid transparent;
}

.project-card__header {
  & h4 {
    font-size: var(--text-lg);
  }
  & p {
    margin-block-end: 10px;
    opacity: 0.7;
  }
}

.project-card__footer {
  .tags {
    margin-block-end: 1rem;
  }
}

body[data-theme='light'] {
  .project-card__content {
    border: var(--border);
  }
}

@media (--vw-sm) {
  .project-card {
    flex-direction: column;
  }
}
</style>
