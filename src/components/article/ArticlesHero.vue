<template>
  
</template>

<style scoped>
.hero {
  background-color: var(--accent-color-lighter, var(--color-gray-800));
  box-shadow: var(--elevation-2);
}

.hero__headline {
  font-size: var(--text-2xl);
}

.hero__description {
  font-size: var(--text-lg);
  max-width: 800px;
}

.container {
  flex-flow: column wrap;
  padding: calc(2rem + 1vw) 0;
}

body[data-theme='light'] .hero {
  box-shadow: var(--elevation-3);
}

@media (--vw-md) {
  .hero .container {
    padding: 1rem 2.4rem;
  }
}
</style>