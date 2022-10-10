<template>
<div class="aerial aerial__grid">
	<div class="aerial__image">
    <img class="aerial__img" :src="aerial_image" alt="Alt Text" loading="lazy">
	</div>
  <div class="aerial__container">
    <div class="aerial__content aerial__content-grid">
      <Highlight
        :highlight_title="grid_title_1"
        :highlight_sub="grid_sub_1"
      />

      <Highlight
        :highlight_title="grid_title_2"
        :highlight_sub="grid_sub_2"
      />

      <Highlight
        :highlight_title="grid_title_3"
        :highlight_sub="grid_sub_3"
      />

      <Headline v-if="typeof aerial_title !== 'undefined'"
        headline_level="h2"
        headline_class="headline headline--uppercase"
        :headline="aerial_title"
      />

      <Highlight
        :highlight_title="grid_title_4"
        :highlight_sub="grid_sub_4"
      />
    </div>
	</div>
</div>
</template>

<script>
import Highlight from './Highlight.vue';
import Headline from './Headline.vue';

export default {
  name: 'Aerial',

  components: {
    Highlight,
    Headline
  },
  
  data() {
    return {
      aerial_title: 'Welcome Home',
      aerial_image: './images/viewbook/sections/12.jpg',
      grid_title_1: 'World-class hospital',
      grid_sub_1: ' A nationally ranked, comprehensive medical center is just a short walk away.',
      grid_title_2: 'Top college town',
      grid_sub_2: 'Named a top 10 college town by U S A Today, Iowa City seamlessly blends the heart of campus with a vibrant downtown that offers a variety of annual festivals, block parties, author readings, and workshops throughout the year.',
      grid_title_3: 'Easy to get around',
      grid_sub_3: ' Whether you like to walk, bike, or take the free bus system, residence halls are closely located to the center of campus and downtown Iowa City.',
      grid_title_4: 'Big ten athletics',
      grid_sub_4: 'Seating nearly 70,000, Kinnick Stadium is home to Hawkeye Football, just one of the 20 NCAA teams at Iowa.'
    }
  }
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/viewbook/aerial/aerial.scss';
</style>
