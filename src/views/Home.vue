<template>
	<div class="home">
		<img alt="Vue logo" src="../assets/logo.png" />
		<Container containerMsg="Who wants to be a Millionaire" />
	</div>
</template>

<script>
	import Container from "@/components/Container.vue";

	export default {
		name: "Home",
		components: {
			Container,
		},
	};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
	img {
		margin-top: 40px;	
		width: 200px;
	}
	.vspace {
		margin: 10px 0;
		padding: 10px;
		border: 1px solid black;
		border-radius: 5px;
	}
</style>
