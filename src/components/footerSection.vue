<template>
<footer class="footer">
	<div class="footer__container footer__container--flex">
		<div class="footer__links footer__links--contact">
			<logo
				logo_id="footer"
				logo_classes="logo--footer"
			></logo>

			<siteName site_name_tag="h2"></siteName>

			<!-- This would be a site slogan -->

			<div v-html="contact_info"></div>

			<div class="footer__links footer__links--icon">
				<menuGroup
					:items="social_media_links"
				></menuGroup>
			</div>

			<div class="socket">
				<ul class="socket__menu">
					<li>
						© {{ new Date().getFullYear() }} The University of Iowa
					</li>
					<li>
						<a href="https://uiowa.edu/privacy">Privacy Notice</a>
					</li>
					<li>
						<a href="https://opsmanual.uiowa.edu/community-policies/nondiscrimination-statement">Nondiscrimination Statement</a>
					</li>
					<li>
						<a href="https://uiowa.edu/accessibility">Accessibility</a>
					</li>
				</ul>
			</div>
		</div>

		<!-- we would render any footer menus here -->

	</div>
</footer>
</template>

<script>
import Logo from './Logo.vue';
import siteName from './siteName.vue';
import menuGroup from './menuGroup.vue';

export default {
    methods: {
	},
	props: ['contact_info', 'social_media_links'],
    components: {
	  Logo,
	  siteName,
	  menuGroup
    }
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/branding/footer/footer.scss';
</style>