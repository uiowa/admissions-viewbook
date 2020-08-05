<template>
  <div class="card__wrapper">
    <template v-for="(area, index) in areas_of_study">
      <hero :headline="area.headline"
            :image="area.image"
            :class="getHeroClasses(index)"
      >
      </hero>
    </template>
  </div>
</template>

<script>
import Hero from "./components/Hero.vue";

export default {
  name: 'App',
  components: {
    Hero,
  },
  data() {
    return {
      areas_of_study: [
        {
          headline: 'Business, Economics, and Management',
          image: 'https://uids.brand.uiowa.edu/branches/feature_admissions_viewbook/assets/images/viewbook/areas/1.jpg',
          link: 'https://admissions.uiowa.edu/academics/biz-econ-mgmt',
        },
        {
          headline: 'Education',
          image: 'https://uids.brand.uiowa.edu/branches/feature_admissions_viewbook/assets/images/viewbook/areas/2.jpg',
          link: 'https://admissions.uiowa.edu/academics/edu',
        },
        {
          headline: '',
          image: '',
          link: 'https://admissions.uiowa.edu/academics/undergraduate-areas-of-study',
        }
      ],
    }
  },
  methods: {
    getHeroClasses(index) {
      console.log('index', index);
      console.log('count', this.areas_of_study.length);
      let classes = 'hero--solid-opacity hero--large hero--row hero--vertical-bottom hero--horizontal-left';
      if (index+1 >= this.areas_of_study.length) {
        classes += ' bg-pattern--brain-black';
      }
      return classes;
    }
  }
}
</script>

<style lang="scss" scoped>
  $imgpath: '../node_modules/@uiowa/uids/src/assets/images';
  @import '../node_modules/@uiowa/uids/src/components/colors/colors.scss';
  @import '../node_modules/@uiowa/uids/src/components/layouts/viewbook/viewbook';
</style>
