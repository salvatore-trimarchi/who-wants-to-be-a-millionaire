<template>
	<div class="container">
		<h1 class="title">{{ containerMsg }}</h1>
		<Question :question="randQuestionDisplay" />
		<Answers :answers="randAnswerDisplay" />
	</div>
</template>

<script>
import Question from "@/components/Question.vue";
import Answers from "@/components/Answers.vue";

export default {
	name: "Container",
	props: {
		containerMsg: String,
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
	.title {
		padding: 30px;
	}
</style>
