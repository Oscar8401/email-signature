<template>
  	<div id="app">
	  	<div class="container">
	  		<app-header title="Adapter Email Signature"/>
			<router-view></router-view>
		</div>
		<footer class="footer">
			<div class="container">
				<p class="text-center">
					Made with <font-awesome-icon :icon="icon"  style="color:pink"/> in Bangkok by <a href="http://github.com/ericprom">Eric Prom</a>
				</p>
			</div>
		</footer>
	</div>
</template>
<script>
import FontAwesomeIcon from '@fortawesome/vue-fontawesome'
import { faHeart } from '@fortawesome/fontawesome-free-solid'
import { Header } from './components/index'

export default {
	computed: {
		icon () {
			return faHeart
		}
	},
	components: {
		FontAwesomeIcon,
		appHeader:Header
	},
};
</script>
<style lang="scss">
@import './assets/sass/custom-bootstrap.scss';
@import '../node_modules/bootstrap/scss/bootstrap.scss';
</style>