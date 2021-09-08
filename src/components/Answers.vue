// %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%% 
// %              COMPONENT: Answers            % 
// %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%% 

// # COMPONENT BODY # 
<template>
	<div class="answers">
		<b-container>
			<b-row class="ans_list">
				<b-col class="ans_item" v-for="(answer,index) in answers" :key="answer" sm="6">
					<div class="qa_block">{{listHead[index]}}. {{ answer }}</div>
				</b-col>
			</b-row>
		</b-container>
	</div>
</template>

// # SOCKETS & PLUGS # 
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

// # COMPONENT STYLE MANAGEMENT # 
<style scoped lang="scss">
//
</style>
