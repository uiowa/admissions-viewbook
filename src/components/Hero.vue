<template>
    <div :class="getHeroClasses(is_last)">
        <div class="hero__image">
            <img :src="image" alt="">
        </div>
        <div class="hero__container">
            <div class="hero__content">
                <headline
                    v-if="hero_title"
                    heading_level="h2"
                    :class="hero_title_classes"
                    :heading="hero_title"
                    :heading_url="link_url"
                ></headline>
                 <div v-html="hero_text"></div>
                 <uids-button
                    v-if="button_text"
                    :button_link="button_link"
                    button_type="bttn bttn--secondary bttn--caps"
                    :button_text="button_text"
                    :button_icon="true">
                </uids-button>
            </div>
        </div>
    </div>
</template>

<script>
import Headline from './headline.vue';
import uidsButton from './uidsButton.vue';

export default {
    props: [
        'image',
        'link_url',
        'is_last',
        'hero_overlay',
        'hero_size',
        'hero_classes',
        'hero_vertical_alignment',
        'hero_horizontal_alignment',
        'hero_text',
        'hero_title',
        'hero_title_classes',
        'button_link',
        'button_text'
        ],
    components: {
        Headline,
        uidsButton
    },
    methods: {
        getHeroClasses(is_last=false) {
            let classes = 'hero hero--'+this.$props.hero_overlay+' hero--'+this.$props.hero_size+' '+this.$props.hero_classes+' hero--'+this.$props.hero_vertical_alignment+' hero--'+this.$props.hero_horizontal_alignment;
            if (is_last) {
                classes += ' bg-pattern--brain-black';
            }
            return classes;
        }
    }
}
</script>

<style lang="scss">
    @import '../../node_modules/@uiowa/uids/src/components/hero/hero.scss';
</style>
