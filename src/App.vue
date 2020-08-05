<template>
  <div class="card__wrapper">
    <template v-for="area in areas_of_study">
      <hero :headline="area.headline"
            :image="area.image"
            class="hero--row hero--solid-opacity hero--large hero--vertical-bottom hero--horizontal-left"
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
        }
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
  @import '../node_modules/@uiowa/uids/src/components/layouts/viewbook/viewbook';
</style>
