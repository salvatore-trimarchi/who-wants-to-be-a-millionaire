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
			arrayShuffleTestCount: {
				'1234': 0,
				'1243': 0,
				'1324': 0,
				'1342': 0,
				'1423': 0,
				'1432': 0,
				'2134': 0,
				'2143': 0,
				'2314': 0,
				'2341': 0,
				'2413': 0,
				'2431': 0,
				'3124': 0,
				'3142': 0,
				'3214': 0,
				'3241': 0,
				'3412': 0,
				'3421': 0,
				'4123': 0,
				'4132': 0,
				'4213': 0,
				'4231': 0,
				'4312': 0,
				'4321': 0,				
				// '123': 0,
				// '132': 0,
				// '213': 0,
				// '231': 0,
				// '321': 0,
				// '312': 0
			},
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
			this.arrayShuffle(this.randAnswerDisplay);
			});
		},
		arrayShuffle(arr) {
			// ////////////////////////////////////////////////////
			// uneven distribution depending on js engine (sort() goes mad)
			// arr.sort(() => Math.random() - 0.5);
			// ////////////////////////////////////////////////////
			// better way
			for (let i = arr.length-1; i>0; i--) {
				let j = Math.floor(Math.random()*(i+1)); // random index from 0 to i
    			[arr[i],arr[j]] = [arr[j],arr[i]]; // swap i-j elements 
			}
			// ////////////////////////////////////////////////////
		},
		arrayShuffleTest() {
			for (let i = 0; i < 10000000; i++) {
				// let array = [1,2,3];
				let array = [1,2,3,4];
				this.arrayShuffle(array);
				this.arrayShuffleTestCount[array.join('')]++;
			}
		},
	},
	computed: {},
	created() {},
	mounted() {
		this.getRndQuestion();
		// this.arrayShuffleTest();
	},
};

</script>

// # COMPONENT STYLE MANAGEMENT # 
<style scoped lang="scss">
//
</style>
