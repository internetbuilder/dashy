<template>
  <!-- User Footer -->
  <footer v-if="text && text !== '' && visible" v-html="text"></footer>
  <!-- Default Footer -->
  <footer v-else-if="visible">
    <span v-if="$store.state.currentConfigInfo" class="path-to-config">
      Using: {{ $store.state.currentConfigInfo.confPath }}
    </span>
    <span>
      {{ $t('footer.dev-by') }} <a :href="authorUrl">{{authorName}}</a>.
      {{ $t('footer.licensed-under') }} <a :href="licenseUrl">{{license}}</a>
      {{ showCopyright? '©': '' }} {{date}}.
      {{ $t('footer.get-the') }} <a :href="repoUrl">{{ $t('footer.source-code') }}</a>.
    </span>
  </footer>
</template>

<script>

import { shouldBeVisible } from '@/utils/SectionHelpers';

export default {
  name: 'Footer',
  props: {
    text: String,
    authorName: { type: String, default: 'Jordan Bourbonnais' },
    authorUrl: { type: String, default: 'https://jordanbourbonnais.com' },
    date: { type: String, default: `${new Date().getFullYear()}` },
    showCopyright: { type: Boolean, default: true },
    repoUrl: { type: String, default: 'https://jordanbourbonnais.com' },
  },
  computed: {
    visible() {
      return shouldBeVisible(this.$route.name);
    },
  },
};
</script>

<style scoped lang="scss">
@import '@/styles/media-queries.scss';

footer {
  width: calc(100% - 0.5rem);
  bottom: 0;
  padding: 0.25rem;
  text-align: center;
  color: var(--medium-grey);
  opacity: var(--dimming-factor);
  background: var(--footer-background);
  margin-top: 1.5rem;
  border-top: 1px solid var(--outline-color);
  @include tablet-down {
    display: none;
  }
  span.path-to-config {
    float: right;
    font-size: 0.75rem;
    margin: 0.1rem 0.5rem 0 0;
    opacity: var(--dimming-factor);
    max-width: 10rem;
    overflow: hidden;
    text-overflow: ellipsis;
    word-break: break-all;
    max-height: 1rem;
  }
}

footer a{
  color: var(--footer-text-color);
  &:hover {
    color: var(--footer-text-color-link);
  }
}

</style>
