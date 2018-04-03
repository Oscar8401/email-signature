<template>
  <div id="app">
	  <div class="container">
	  	<app-header title="Adapter Email Signature"/>
			<router-view></router-view>
		</div>
	</div>
</template>

<script>
import { Header } from './components/index'
export default {
	components: {
			appHeader:Header
	},
};
</script>
<style lang="scss">
@import '../node_modules/bootstrap/scss/bootstrap.scss';
</style>