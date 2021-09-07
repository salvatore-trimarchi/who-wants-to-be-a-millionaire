<template>
	<div class="question">
		<!-- <h2>Question:</h2> -->
		<b-container>
			<b-row>
				<b-col>
					<div class="block">{{ question }}</div>
				</b-col>
			</b-row>
		</b-container>
	</div>
</template>

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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
//
</style>
