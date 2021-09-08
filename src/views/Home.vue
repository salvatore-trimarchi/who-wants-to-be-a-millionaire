// %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%% 
// %               COMPONENT: Home              % 
// %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%% 

// # COMPONENT BODY # 
<template>
	<div class="home">
		<div class="header">
			<img src="../assets/logo.png" alt="logo" />
		</div>
		<Container containerTitle="Who wants to be a Millionaire" />
	</div>
</template>

// # SOCKETS & PLUGS # 
<script>

import Container from "@/components/Container.vue";

export default {
	name: "Home",
	components: {
		Container,
	},
};

</script>

// # COMPONENT STYLE MANAGEMENT # 
<style scoped lang="scss">
//
</style>
