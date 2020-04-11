<template>
	<div>
		<div class="uk-height-large uk-background-cover uk-flex" uk-parallax="bgy: -200" :style="{
			'background-image': `url('../assets/images/dark.jpg')`
		}">
			<h1 class="uk-width-1-2@m uk-text-center uk-margin-auto uk-margin-auto-vertical">Headline</h1>
		</div>
	</div>
</template>

<script type="text/javascript">
	export default {
		name: 'home',
		computed: {
			url() {
				return document.location.origin;
			}
		}
	}
</script>
