<template>
    <div class="hero">
        <div class="hero__image">
            <img :src="image" alt="">
        </div>
        <div class="hero__container">
            <div class="hero__content">
                <headline v-if="headline"
                          heading_level="h2"
                          class="bold-headline--caps bold--headline bold-headline--highlight"
                          :heading="headline"
                          :heading_url="link"
                ></headline>
            </div>
        </div>
    </div>
</template>

<script>
import Headline from './headline.vue';

export default {
    props: ['headline', 'image', 'link'],
    components: {
        Headline,
    }
}
</script>

<style lang="scss" scoped>
    @import '../../node_modules/@uiowa/uids/src/components/hero/hero.scss';
</style>