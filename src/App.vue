<template>
<div id="app" class="app">
	<div class="header">
		<div class="header-content">
			<router-link to="/"><img src="@/assets/logo.svg" alt="W" class="logo"></router-link>
			<div class="nav">
				<router-link to="/about" class="nav-item">About</router-link>
				<a href="mailto:hi@designbywillj.com" target="_blank" class="nav-item">Contact</a>
				<a href="https://drive.google.com/open?id=1MSItOhQLsdyca3GwFVlhzE-lQP3SPvGr" target="_blank" class="nav-item">Resume</a>
			</div>
		</div>
	</div>

	<transition name="fade" mode="out-in">
		<router-view/>
	</transition>

	<div class="footer">
		<div class="socials">
			<a href="https://facebook.com/designbywillj" target="_blank"><h3>Facebook.</h3></a>
			<a href="https://instagram.com/designbywillj" target="_blank"><h3>Instagram.</h3></a>
			<a href="https://twitter.com/designbywillj" target="_blank"><h3>Twitter.</h3></a>
		</div>
		<h3>Will Johnson &#169; 2019</h3>
	</div>
</div>
</template>

<script>
export default {
	mounted()
	{
		window.onload = this.handleLoad;
	},

	methods: {
		handleLoad()
		{
			const splash = document.getElementById('splash');
			splash.className = 'splash';
			setTimeout(this.removeSplash, 1000, splash);
		},

		removeSplash(splash)
		{
			splash.parentNode.removeChild(splash);
		}
	}
}
</script>


<style>
@import url('./css/font.css');
@import url('./css/reset.css');
@import url('./css/header.css');
@import url('./css/footer.css');
@import url('./css/about.css');
@import url('./css/casestudy.css');

.fade-enter-active,
.fade-leave-active {
	transition: opacity .5s ease-in-out;
}

.fade-enter,
.fade-leave-active {
	opacity: 0;
}
</style>
