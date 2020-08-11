<template>
  <header class="iowa-bar" :class="IowaBarClasses(parent_site.name, iowa_bar_classes)">
    <div class="iowa-bar__container">

      <logo
        logo_id="header"
        logo_classes="logo--tab"
      ></logo>

    </div>
  </header>

// <header class="{{ classes }}" data-uids-header>
//   <div class="iowa-bar__container">
//     This is where we would print a parent site name or an inline site name
//     {% block top_links %}
//     {% endblock %}
//     {% block off_canvas %}
//     {% endblock %}
//   </div>
//   {% if site_name_position == 'below' or below_bar_content is not empty %}
//   {% block below_bar %}
//     <div class="iowa-bar__below">
//       <div class="iowa-bar__container">
//         {% if site_name and site_name_position == 'below' %}
//           {% include '@site-name' %}
//         {% endif %}
//         {{ below_bar_content }}
//       </div>
//     </div>
//   {% endblock %}
//   {% endif %}
// </header>


</template>

<script>
import Logo from './Logo.vue';

export default {
    props: ['iowa_bar_classes', 'parent_site'],
    components: {
      Logo
    },
    methods: {
      IowaBarClasses(name, iowa_bar_classes) {
        return (name.length > 0) ? iowa_bar_classes + ' ' + 'iowa-bar--narrow' : iowa_bar_classes;
      }
    }
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/branding/iowa-bar/iowa-bar.scss';
</style>