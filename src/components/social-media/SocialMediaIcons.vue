<template>
  <div :class="classes">
    <AppLink isExternal to="https://github.com/DwiHerzaa" aria-label="My Github" title="My Github">
      <svg width="30" height="30" viewBox="0 0 44 44" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path
          d="M21.9805 0.725586C9.90527 0.720703 0.125 10.4961 0.125 22.5615C0.125 32.1025 6.24316 40.2129 14.7637 43.1914C15.9111 43.4795 15.7354 42.6641 15.7354 42.1074V38.3232C9.10938 39.0996 8.84082 34.7148 8.39648 33.9824C7.49805 32.4492 5.37402 32.0586 6.00879 31.3262C7.51758 30.5498 9.05566 31.5215 10.8379 34.1533C12.127 36.0625 14.6416 35.7402 15.916 35.4229C16.1943 34.2754 16.79 33.25 17.6104 32.4541C10.7451 31.2236 7.88379 27.0342 7.88379 22.0537C7.88379 19.6367 8.67969 17.415 10.2422 15.623C9.24609 12.6689 10.335 10.1396 10.4814 9.76367C13.3184 9.50977 16.2676 11.7949 16.4971 11.9756C18.1084 11.541 19.9492 11.3115 22.0098 11.3115C24.0801 11.3115 25.9258 11.5508 27.5518 11.9902C28.1035 11.5703 30.8379 9.60742 33.4746 9.84668C33.6162 10.2227 34.6807 12.6934 33.7432 15.6084C35.3252 17.4053 36.1309 19.6465 36.1309 22.0684C36.1309 27.0586 33.25 31.2529 26.3652 32.4639C26.9549 33.0438 27.4232 33.7354 27.7426 34.4983C28.062 35.2612 28.2262 36.0801 28.2256 36.9072V42.4004C28.2646 42.8398 28.2256 43.2744 28.958 43.2744C37.6055 40.3594 43.8311 32.1904 43.8311 22.5664C43.8311 10.4961 34.0459 0.725586 21.9805 0.725586Z"
          fill="#F4F4F4" />
      </svg>
    </AppLink>
    
  </div>
</template>

<script setup>
import { computed, defineProps } from 'vue'

const props = defineProps({
  boxed: {
    type: Boolean,
    default: false,
  },
})

const classes = computed(() => ({
  'social-media-icons': true,
  'social-media-icons--boxed': props.boxed,
}))
</script>

<style scoped>
body[data-theme='light'] {
  .social-media-icons a {

    svg,
    svg path {
      fill: var(--color-default-black);
    }
  }
}

.social-media-icons {
  display: flex;
  align-items: center;

  & a {
    border-radius: var(--radius-default);
    padding: 0.25rem 0.5rem;
    outline: 0;

    &:hover,
    &:focus {
      transform: translateY(-4px);
    }

    &:hover svg,
    &:focus svg,
    &:hover svg path,
    &:focus svg path {
      fill: var(--color-primary);
    }
  }

  & a+a {
    margin-inline-start: 20px;
  }

  & :is(a, svg, path) {
    transition-duration: 400ms;
    transition-timing-function: cubic-bezier(0.22, 0.61, 0.36, 1);
    transition-property: transform, fill, box-shadow;
    will-change: transform;
  }
}

.social-media-icons--boxed {
  a {
    display: inline-block;
  }
}

@media (--vw-sm) {
  .social-media-icons {
    justify-content: center;
  }
}
</style>
