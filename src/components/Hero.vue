<template>
    <div :class="getHeroClasses(is_last)">
        <div class="hero__image">
            <img :src="image" alt="">
        </div>
        <div class="hero__container">
            <div class="hero__content">
                <Headline
                    v-if="hero_title"
                    heading_level="h2"
                    :class="hero_title_classes"
                    :heading="hero_title"
                    :heading_url="link_url"
                />
                 <div v-html="hero_text"></div>
                 <linkButton
                    v-if="button_text"
                    :button_link="button_link"
                    button_type="bttn bttn--secondary bttn--caps"
                    :button_text="button_text"
                    :button_icon="true"
                />
            </div>
        </div>
    </div>
</template>

<script>
import Headline from './headline.vue';
import linkButton from './linkButton.vue';

export default {
    name: 'Hero',

    props: {
        image: {
            type: String
        },
        link_url: {
            type: String
        },
        is_last: {
            type: Boolean
        },
        hero_overlay: {
            type: String
        },
        hero_size: {
            type: String
        },
        hero_classes: {
            type: String
        },
        hero_vertical_alignment: {
            type: String
        },
        hero_horizontal_alignment: {
            type: String
        },
        hero_text: {
            type: String
        },
        hero_title: {
            type: String
        },
        hero_title_classes: {
            type: String
        },
        button_link: {
            type: String
        },
        button_text: {
            type: String
        }
    },

    components: {
        Headline,
        linkButton
    },

    methods: {
        /* 
            This method takes a boolean 'is_last' (defaulted to false).
            It composes a string out of the classes passed to the component, and then if 'is_last' is true it will add some for that case.
        */
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
