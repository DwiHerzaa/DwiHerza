<template>
  <div class="container">
    <main id="main-content">
      <article class="about-content">
        <picture>
          <img src="@/assets/img/profile.jpg" alt="me" width="140" height="190" loading="lazy" />
        </picture>
        <h1 class="about-content__headline">About me</h1>

        <p>
          👋 Hai! Apa kabar guys?
          Saya Dwi Herza Anugrah. Saya
          <strong>Mahasiswa Universitas Islam Riau</strong> Saya
          <em> Berkuliah </em> pada tahun 2022
        </p>
        <p>
          Ini Pertama kalinya saya membuat portofolio menggunakan website, saya mempunyai skill di bidang website tapi blm punya pengalaman dalam membikin projek
        </p>
        <p>
          Saya memiliki favorit game GTA V, FIFA, dan God Of War 
        </p>
        <p>Secara personal sangat biasa menggunakan komputer, bermain game, pecinta film</p>
      </article>
      <SocialMediaIcons boxed />
    </main>
  </div>
</template>

<script setup>
import { useRoute } from 'vue-router'
import config from '../config/siteconfig.json'

const title = 'About me • Dwi Herzaa'
const { description } = config
const route = useRoute()

useHead({
  title,
  meta: [
    {
      name: 'description',
      content: description,
    },
    { property: 'og:type', content: 'website' },
    { property: 'og:title', content: title },
    { property: 'og:description', content: description },
    { property: 'og:url', content: `${config.siteUrl}${route.path}` },
    {
      property: 'twitter:title',
      content: title,
    },
    {
      property: 'twitter:description',
      content: description,
    },
  ],
})
</script>

<route lang="yaml">
meta:
  layout: default
</route>

<style lang="css" scoped>
.container {
  flex-flow: row wrap;
  padding: 3rem 0;
  gap: 2.4rem;
}

.about-content {
  margin-block-end: 2rem;

  & picture {
    float: left;
    shape-outside: ellipse(50% 50%);
    margin: 0 1.125rem 0 0;
    position: relative;

    & img {
      max-width: 140px;
      clip-path: circle(70px at center);
      object-fit: cover;
    }

    &::before {
      content: '';
      position: absolute;
      display: block;
      width: 155px;
      height: 155px;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) rotate(0deg);
      outline: 3px inset var(--color-silver);
      border-radius: 9999px;
      will-change: transform;
    }
  }

  & .about-content__headline {
    font-size: var(--text-2xl);
  }

  & p {
    font-size: var(--text-lg);
    opacity: 0.8;
    max-width: 71ch;
    margin-top: 0.50em;
  }
}

.binary-text-svg {
  font-family: var(--font-mono);
  font-size: var(--text-xl);
  position: absolute;
  left: 282px;
  top: 387px;
  opacity: 0.3;

  & :deep(tspan) {
    --text-delay: 500ms;

    opacity: 0;
    animation: pulse-spread 3s var(--text-delay) ease-out infinite alternate;

    &:nth-child(1) {
      --text-delay: 500ms;
    }

    &:nth-child(2) {
      --text-delay: 1s;
    }

    &:nth-child(3) {
      --text-delay: 1.5s;
    }

    &:nth-child(4) {
      --text-delay: 2s;
    }

    &:nth-child(5) {
      --text-delay: 2.5s;
    }

    &:nth-child(6) {
      --text-delay: 3s;
    }
  }
}

@keyframes pulse-spread {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 0.3;
  }
}

@media screen and (min-width: 26.625em) and (max-width: 48em) {
  aside {
    margin-inline-start: 40px;
    padding: 0 2.4rem 0 0;
  }
}

@media (--vw-sm) {
  aside {
    padding: 0 1rem;
  }

  .container {
    height: 100%;
  }

  .binary-text-svg {
    top: 50%;
    left: 0;
    bottom: 0;
  }
}
</style>
