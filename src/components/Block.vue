<template>
  <div class="block" v-if="showBlock">
    click me
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Block",
  props: ['delay'],
  data() {
    return {
      showBlock: false,
    } 
  },
  mounted() {
    console.log("component mounted")
    setTimeout(() => {
      this.showBlock = true
      console.log(this.delay)
    }, this.delay)
  },
  updated() {
    console.log("component updated");
    // console.log(this.delay);
    // setTimeout(() => {
    //   this.showBlock = true;
    // }, this.delay);
  },
  unmounted() {
    console.log("component unmounted");
  },
};
</script>

<style scoped>
  .block {
    width: 400px;
    border-radius: 20px;
    background: #0faf87;
    color: #fff;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
  }
</style>