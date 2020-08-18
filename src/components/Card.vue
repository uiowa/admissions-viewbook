<template>
    <div class="card">
        <div v-if="image" class="card__media">
            <a v-if="link_element == 'image'" :href="card_link_url">
                <img class="card__img" :src="image" alt="Alt Text">
            </a>
            <img v-else class="card__img" :src="image" alt="Alt Text">
        </div>

        <div class="card__body">
            <Headline v-if="card_title !== ''"
                heading_level="h2"
                heading_class="card__title"
                :heading="card_title"
                :heading_url="card_link_url"
                :heading_aria="card_aria"
            />

            <div v-if="card_author!==''" class="card__author">{{ card_author }}</div>

            <p v-html="card_content"></p>

            <template v-if="card_link_url !== '' && show_button">
                <template v-if="link_element == 'button'">
                    <linkButton
                        :button_link = "card_link_url"
                        button_type = "bttn--full bttn--outline bttn--tertiary bttn--sans-serif"
                        :button_text = "card_link_title"
                        :button_icon = "true"
                    />
                </template>
                <template v-else>
                    <!-- This should eventually have JS attached o it to click the right thing. -->
                    <div aria-hidden="true" class="bttn bttn--full bttn--outline bttn--tertiary bttn--sans-serif" :id="card_aria!=='' ? card_aria :''">
                        {{ card_link_title }}
                        <i class="fas fa-arrow-right"></i>
                    </div>
                </template>
            </template>
        </div>
    </div>
</template>

<script>
import Headline from './Headline.vue';
import linkButton from './linkButton.vue';

// Set the card data object.
let card_data = {
    card_classes: 'card--enclosed', // Should start as empty string.
    card_image: "https://antarasdiary.com/wp-content/uploads/2011/04/cute-bunny-photographs.jpg", // Should start as empty string.
    card_title: 'Hello World!',
    card_link_url: "https://google.com", // Should start as empty string.
    card_link_title: 'This is the card link title', // Should start as empty string.
    link_element: false,
    show_button: false,
    card_aria: 'Card Aria',
    card_author: 'Alan Ridgway',
    card_content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam condimentum nunc ultrices pellentesque rhoncus. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Etiam sagittis ipsum ex. Donec sit amet ipsum quis sapien tempus cursus aliquam vel magna. Maecenas ut leo finibus, consequat eros sit amet, tempor ligula. Etiam vitae mattis lectus. Nunc condimentum augue tortor, ac ornare magna congue vitae.',
};

// Set dynamic properties of link_element and show_button.
if (card_data.card_link_url !== '') {
    if (card_data.card_title !== '') {
        // Title is set, use it as the linking element.
        card_data.link_element = 'title';
        // If we also have link text, then we'll show a psuedo-button.
        if (card_data.card_link_title !== '') {
            card_data.show_button = true;
        }
    }
    else if (card_data.card_link_title !== '') {
        // Title is not set, but there is link text, so use that instead.
        card_data.link_element = 'button';
        // Show an actual link button.
        card_data.show_button = true;
    }
    else if (card_data.card_image !== '') {
        // If the image exists, use that as the linking element.
        card_data.link_element = 'image';
    }
    else {
        // Nothing else to use, so wrap the whole card.
        card_data.link_element = 'card';
    }
}

export default {
    name: 'Card',

    props: {
        image: {
            type: String
        },
        title: {
            type: String
        },
        link_url: {
            type: String
        },
        link_title: {
            type: String
        },
        aria: {
            type: String
        },
        author: {
            type: String
        },
        content: {
            type: String
        }
    },

    components: {
        Headline,
        linkButton,
    },

    data() {
        return card_data
    },

    // This will attack a click listener on this card if it has one of the classes listed in 'link_elements'.
    created() {
        this.$nextTick(() => {
            const element = this.$el;
            const link_elements = ['.card__title a', '.card__media a', 'a.bttn'];
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
}
</script>

<style lang="scss">
  @import '../../node_modules/@uiowa/uids/src/components/card/card.scss';
</style>