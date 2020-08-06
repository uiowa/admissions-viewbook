<template>
<<<<<<< HEAD
  <component :is="heading_level" :class="heading_class">
    <a v-if="heading_url" :href="heading_url" :aria-describedby="heading_aria ? heading_aria :''">
      <span v-if="heading_prefix" class="heading__prefix">{{heading_prefix}}</span>
      <span class="heading__heading">{{heading}}</span>
      <span v-if="heading_suffix" class="heading__suffix">{{heading_suffix}}</span>
    </a>
    <template v-else>
      <span v-if="heading_prefix" class="heading__prefix">{{heading_prefix}}</span>
      <span class="heading__heading">{{heading}}</span>
      <span v-if="heading_suffix" class="heading__suffix">{{heading_suffix}}</span>
    </template>
  </component>
=======
    <component :is="heading_level" :class="heading_class">
        <a v-if="heading_url" :href="heading_url" :aria-describedby="heading_aria ? heading_aria :''">
            <span v-if="heading_prefix" class="heading__prefix">{{heading_prefix}}</span>
            <span v-html="heading" class="heading__heading"></span>
            <span v-if="heading_suffix" class="heading__suffix">{{heading_suffix}}</span>
        </a>
        <template v-else>
            <span v-if="heading_prefix" class="heading__prefix">{{heading_prefix}}</span>
            <span v-html="heading" class="heading__heading"></span>
            <span v-if="heading_suffix" class="heading__suffix">{{heading_suffix}}</span>
        </template>
    </component>
>>>>>>> added headline
</template>

<script>

export default {
  name: 'Headline',
  props: {
    heading_level: {
      type: String,
    },
    heading_class: {
      type: String,
    },
    heading: {
      type: String,
    },
    heading_url: {
      type: String,
    },
    heading_aria: {
      type: String,
    },
    heading_prefix: {
      type: String,
    },
    heading_suffix: {
      type: String,
    },
  }
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/headline/headline.scss';
</style>