// %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%% 
// %             COMPONENT: Container           % 
// %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%% 

// # COMPONENT BODY # 
<template>
	<div class="qa_container">
		<!-- <h1 class="title">{{ containerTitle }}</h1> -->
		<div class="qa_box">
			<Question :question="randQuestionDisplay" />
			<Answers :answers="randAnswerDisplay" />
		</div>
	</div>
</template>

// # SOCKETS & PLUGS # 
<script>

import Question from "@/components/Question.vue";
import Answers from "@/components/Answers.vue";

export default {
	name: "Container",
	props: {
		containerTitle: String,
	},
	components: {
		Question,
		Answers,
	},
	data() {
		return {
		randQuestionDisplay: null,
		randAnswerDisplay: [],
		};
	},
	methods: {
		getRndQuestion() {
		let wl = window.location;
		this.axios
			.get(wl.protocol + "//" + wl.host + wl.pathname + "api/qalist.json", {})
			.then((resp) => {
			// correct answer is always the first in answer array
			console.log("resp.data =", resp.data);
			let N = resp.data.length;
			let randQuestNum = Math.floor(Math.random() * (N - 0) + 0);
			this.randQuestionDisplay = resp.data[randQuestNum].question;
			this.randAnswerDisplay = resp.data[randQuestNum].answers;
			this.shuffle(this.randAnswerDisplay);
			});
		},
		shuffle(arr) {
		arr.sort(() => Math.random() - 0.5);
		},
	},
	computed: {},
	created() {},
	mounted() {
		this.getRndQuestion();
	},
};

</script>

// # COMPONENT STYLE MANAGEMENT # 
<style scoped lang="scss">
//
</style>
