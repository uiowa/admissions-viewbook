<template>
<li class="menu-item">
  <a :href="url" :class="item_class"><span class="link-text">{{text}}</span></a>
  <!-- We would render submenu Items here -->
  <!-- {% if item.children %}
    {# If there is a child menu under this link, render it. #}
    {% include "@menu" with { items: item.children} %}
  {% endif %} -->
</li>
</template>

<script>
export default {
    props: ['text', 'url', 'item_class'],
}
</script>

<style lang="scss">
</style>

link_bttn:
    items:
      - text: Apply Now
        url: https://admissions.uiowa.edu/apply/first-year-student-application-process
        item_class: bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--apply
      - text:  Schedule a Visit
        url: https://admissions.uiowa.edu/visit-campus
        item_class: bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--visit
      - text: Contact Us
        url: https://admissions.uiowa.edu/contact-us
        item_class: bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--ask
      - text: Request Information
        url: https://www.maui.uiowa.edu/maui/pub/admissions/webinquiry/undergraduate.page
        item_class: bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--connect