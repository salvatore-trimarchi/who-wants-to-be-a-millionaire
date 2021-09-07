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
  width: 200px;
}
</style>
