<template>
  <footer class="footer">
    <div class="container">
      <p class="footer__copyright">
        <em>Made by DwiHerzaa</em>
        <span>@2024 - Present. All rights reserved.</span>
      </p>
      <div class="built-tech">
        <AppLink to="https://github.com/DwiHerzaa" aria-label="Source Code on Github" isExternal>
          <OctocatSVG />
        </AppLink>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  padding-block: 1rem;
  border-top: 1px solid hsla(214, 9%, 25%, 0.2);
  margin-block-start: 40px;
}

.footer .container {
  flex-wrap: wrap;
  gap: 1rem;
  align-items: center;
  justify-content: space-between;
}

.footer__copyright {
  & em {
    text-emphasis: unset;
    font-style: normal;
    font-weight: var(--fw-bold);
    margin-inline-end: 0.25rem;
  }

  & span {
    font-weight: var(--fw-bold);
    opacity: 0.6;
    color: var(--text-color-default);
  }
}

.built-tech {
  & svg {
    display: inline-block;
    width: 40px;
  }

  a {
    vertical-align: middle;
  }

  a+a {
    margin-inline-start: 1rem;
  }
}

@media (--vw-lg) {
  .footer {
    font-size: var(--text-base);
  }
}

@media (--vw-sm) {
  .container {
    text-align: center;
  }

  .footer__copyright {
    order: 2;
  }

  .built-tech {
    order: 1;
    flex-basis: 100%;
  }
}
</style>
