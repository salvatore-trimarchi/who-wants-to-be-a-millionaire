<template>
  <div class="answers">
    <h2>Answers:</h2>
    <div class="ans_list">
      <div class="ans_item" v-for="answer in answers" :key="answer">
        {{ answer }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Answers",
  props: {
    answers: Array,
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.answers {
	.ans_list {
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		border: 1px solid red;
		.ans_item {
			width: 45%;
			border: 1px solid red;
	  }
	}
}
</style>
