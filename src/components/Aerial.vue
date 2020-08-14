<template>
<div class="aerial aerial__grid">

	<div class="aerial__image">
    <img class="aerial__img" :src="aerial_image" alt="Alt Text">
	</div>
  <div class="aerial__container">
    <div class="aerial__content aerial__content-grid">
      <Highlight
        :highlight_title="grid_title_1"
        :highlight_sub="grid_sub_1"
      ></Highlight>

      <Highlight
        :highlight_title="grid_title_2"
        :highlight_sub="grid_sub_2"
      ></Highlight>

      <Highlight
        :highlight_title="grid_title_3"
        :highlight_sub="grid_sub_3"
      ></Highlight>

      <headline v-if="typeof aerial_title !== 'undefined'"
        heading_level="h2"
        heading_class="bold-headline--caps bold-headline"
        :heading="aerial_title"
      />

      <Highlight
        :highlight_title="grid_title_4"
        :highlight_sub="grid_sub_4"
      ></Highlight>
  </div>

	</div>

</div>
</template>

<script>
import Highlight from './Highlight.vue';
import headline from './headline.vue';

export default {
  name: 'Aerial',
  components: {
    Highlight,
    headline
  },
  data() {
    return {
      aerial_title: 'Welcome Home',
      aerial_image: '../src/assets/images/viewbook/sections/12.jpg',
      grid_title_1: 'World-class hospital',
      grid_sub_1: ' A nationally ranked, comprehensive medical center is just a short walk away.',
      grid_title_2: 'Best college town',
      grid_sub_2: 'Named the #1 Best College Town by reviews.org, Iowa City seamlessly blends a vibrant downtown with the heart of campus.',
      grid_title_3: 'Easy to get around',
      grid_sub_3: ' Whether you like to walk, bike, or take the free bus system, residence halls are closely located to the center of campus and downtown Iowa City.',
      grid_title_4: 'Big ten athletics',
      grid_sub_4: 'Seating nearly 70,000, Kinnick Stadium is home to Hawkeye Football, just one of the 24 NCAA teams at Iowa.'
    }
  }
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/aerial/aerial.scss';
</style>
