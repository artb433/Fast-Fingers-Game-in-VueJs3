<template>
  <div class="block">
    click me
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Block",
  created() {},
  data() {
    return {};
  },
  props: ['delay'],
  methods: {},
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