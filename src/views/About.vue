<template>
  <article class="about">
    
  </article>
</template>

<script>
document.getElementsByTagName('html')[0].setAttribute('data-theme', 'callisto');
</script>

<style scoped lang="scss">

article.about {
  background: var(--about-page-background);
  color: var(--about-page-color);
  width: 80%;
  max-width: 1000px;
  margin: 1rem auto 2.5rem auto;
  padding: 1rem;
  border: 1px solid var(--about-page-accent);
  border-radius: var(--curve-factor);
  h1, h2, h3, p, span, div, section {
    color: var(--about-page-color);
  }
  h1 {
    font-size: 2rem;
    text-align: center;
  }
  a, code {
    color: var(--about-page-accent);
  }
  section {
    padding-bottom: 1rem;
    &:not(:last-child) {
      border-bottom: 1px dashed var(--about-page-accent);
    }
  }
  p {
    line-height: 1.5rem;
    font-size: 1rem;
  }
  img.aht-pic {
    width: 100px;
    float: right;
  }
  section.license code {
    color: var(--about-page-color);
  }
}

</style>
