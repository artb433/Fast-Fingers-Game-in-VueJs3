<template>
  <p>{{ rank }}</p>
</template>

<script>
export default {
  name: "ResultsConponent",
  created() {},
  data() {
    return {
      rank: null
    };
  },
  mounted() {
    if(this.score < 250){
      this.rank = "Ninja Fingers"
    } else if(this.score < 500){
      this.rank = "Super Human"
    } else if(this.score < 1000){
      this.rank = "Average Human"
    } else if(this.score < 2000){
      this.rank = "Slow Human"
    } else {
      this.rank = "Slowest Human"

    }
  },
  props: ['score'],
  methods: {},
};
</script>

<style scoped>
p {

  width: 300px;
  border-radius: 20px;
  font-size: 1.4em;
  background: #0faf87;
  color: #fff;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
.rank {
  font-size: 1.4em;
  color: #0faf87;
  font-weight: bold;
}
</style>