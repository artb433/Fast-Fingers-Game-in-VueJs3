<template>
<div><h1>{{title}}</h1></div>

<input type="text" ref="name">
<button @click="toggleModal">Click Me</button>
<div v-if="showModal">
  <Modal :header="header" :content="content" @close="toggleModal"/>
</div>
</template>

<script>
import Modal from './components/Modal.vue'


export default {
  name: 'App',
  components: {
    Modal,
  },
  data() {
    return {
      title: 'ART.B  TECHNOLOGIES',
      header: 'Sign Up To Continue',
      content: 'You are one step away from being part of this great journey',
      showModal: false,
    }
  },
  methods: {
    toggleModal() {
    this.showModal = !this.showModal
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} 

h1 {
border-bottom: 1px solid #ddd;
display: inline-block;
padding-bottom: 10px;
color: black;
}
</style>
