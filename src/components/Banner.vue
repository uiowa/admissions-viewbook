<template>
    <div :class="getBannerClasses(is_last)">
        <div class="banner__image">
            <img :src="image" alt="" loading="lazy">
        </div>
        <div class="banner__container">
            <div class="banner__content">
                <Headline
                    v-if="banner_title"
                    headline_level="h2"
                    :class="banner_title_classes"
                    :headline="banner_title"
                    :headline_url="link_url"
                />
                 <div v-html="banner_text"></div>
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
import Headline from './Headline.vue';
import linkButton from './linkButton.vue';

export default {
    name: 'Banner',

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
        banner_overlay: {
            type: String
        },
        banner_size: {
            type: String
        },
        banner_classes: {
            type: String
        },
        banner_vertical_alignment: {
            type: String
        },
        banner_horizontal_alignment: {
            type: String
        },
        banner_text: {
            type: String
        },
        banner_title: {
            type: String
        },
        banner_title_classes: {
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

    // This will attack a click listener on this hero if it has one of the classes listed in 'link_elements'.
    created() {
        this.$nextTick(() => {
            const element = this.$el;
            const link_elements = ['.headline a', 'a.bttn'];
            let up, down, link, i;
            // Check if it has one of the classes defined in 'link_elements'.
            for (i = 0; i < link_elements.length; i++) {
                if (link = element.querySelector(link_elements[i])) {
                    break;
                }
            }

            // If we have a match, attach behaviors.
            if (link) {
                element.style.cursor = 'pointer';
                element.onmousedown = () => down = +new Date();
                element.onmouseup = () => {
                    up = +new Date();
                    // Trigger click event if the click duration is short enough.
                    if ((up - down) < 200) {
                        link.click();
                    }
                }
            }
        });
    },

    methods: {
        /* 
            This method takes a boolean 'is_last' (defaulted to false).
            It composes a string out of the classes passed to the component, and then if 'is_last' is true it will add some for that case.
        */
        getBannerClasses(is_last=false) {
            let classes = 'banner banner--'+this.$props.banner_overlay+' banner--'+this.$props.banner_size+' '+this.$props.banner_classes+' banner--'+this.$props.banner_vertical_alignment+' banner--'+this.$props.banner_horizontal_alignment;
            if (is_last) {
                classes += ' bg-pattern--brain-black';
            }
            return classes;
        }
    }
}
</script>

<style lang="scss">
    @import '../../node_modules/@uiowa/uids/src/components/banner/banner.scss';
</style>
