// %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%% 
// %             COMPONENT: Question            % 
// %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%% 

// # COMPONENT BODY # 
<template>
	<div class="question">
		<b-container>
			<b-row>
				<b-col>
					<div class="qa_block">{{ question }}</div>
				</b-col>
			</b-row>
		</b-container>
	</div>
</template>

// # SOCKETS & PLUGS # 
<script>

export default {
	name: "Question",
	props: {
		question: String,
	},
	data() {
		return {};
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
