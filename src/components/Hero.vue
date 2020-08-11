<template>
    <div :class="getHeroClasses(is_last)">
        <div class="hero__image">
            <img :src="image" alt="">
        </div>
        <div class="hero__container">
            <div class="hero__content">
                <headline v-if="headline"
                          heading_level="h2"
                          class="bold-headline--caps bold-headline bold-headline--highlight"
                          :heading="headline"
                          :heading_url="link_url"
                ></headline>
            </div>
        </div>
    </div>
</template>

<script>
import Headline from './headline.vue';

export default {
    props: ['headline', 'image', 'link_url', 'is_last'],
    components: {
        Headline,
    },
    methods: {
        getHeroClasses(is_last) {
            let classes = 'hero hero--solid-opacity hero--large hero--row hero--vertical-bottom hero--horizontal-left';
            if (is_last) {
                classes += ' bg-pattern--brain-black';
            }
            return classes;
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../../node_modules/@uiowa/uids/src/components/hero/hero.scss';
</style>
