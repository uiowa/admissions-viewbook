<template>
  <div class="stat__grid stat--horizontal">
    <div>
      <Headline
        v-if="headline"
        headline_level="h2"
        class="stat__title"
        :headline="headline"
        :headline_prefix="headline_prefix"
        :headline_suffix="headline_suffix"
      />
    </div>
    <p v-html="stat_description" class="stat__description"></p>
    <p v-html="stat_content" class="stat__content"></p>
  </div>
</template>

<script>
import Headline from './Headline.vue';

export default {
    name: 'Stat',

    props: {
      headline: {
        type: String
      },
      headline_prefix: {
        type: String
      },
      headline_suffix: {
        type: String
      },
      image: {
        type: String
      },
      link_url: {
        type: String
      },
      stat_description: {
        type: String
      },
      stat_content: {
        type: String
      }
    },

    components: {
        Headline,
    }
}
</script>

<style lang="scss">
    @import '../../node_modules/@uiowa/uids/src/components/stat/stat.scss';
</style>
