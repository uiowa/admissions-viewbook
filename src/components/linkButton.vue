<template>
    <a :href="button_link" class="bttn" :class= "button_type">
        {{button_text}}
        <i v-if="button_icon" class="fas fa-arrow-right"></i>
    </a>
</template>

<script>

export default {
    name: 'linkButton',
    
    props: {
        button_link: {
            type: String,
        },
        button_type: {
            type: String,
        },
        button_text: {
            type: String,
        },
        button_icon: {
            type: Boolean,
        },
    }
}
</script>
<style lang="scss">
    @import '../../node_modules/@uiowa/uids/src/components/button/button.scss';
</style>