<template>
	<div class="answers">
		<!-- <h2>Answers:</h2> -->
		<b-container>
			<b-row class="ans_list">
				<b-col class="ans_item" v-for="(answer,index) in answers" :key="answer" sm="6">
					<div class="block">{{listHead[index]}}. {{ answer }}</div>
				</b-col>
			</b-row>
		</b-container>
	</div>
</template>

<script>
export default {
	name: "Answers",
	props: {
		answers: Array,
	},
	data() {
		return {
			listHead: ['A','B','C','D']
		};
	},
	methods: {},
	computed: {},
	created() {},
	mounted() {},
	};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
//
</style>
