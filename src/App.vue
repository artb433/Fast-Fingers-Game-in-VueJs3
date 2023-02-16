<template>
<div><h1>{{title}}</h1></div>
<button @click="toggleModal">Click Me</button>
<button @click="toggleModal2">Sign In</button>
<div v-if="showModal">
  <Modal theme="sale" @close="toggleModal">
    <template v-slot:links>
      <a href="#">Sign Up Now</a>
      <a href="#">More Info</a>
    </template>
    <h1>{{header}}</h1>
    <p>{{text}}</p>
  </Modal>
</div>
<div v-if="showModal2">
  <Modal  @close="toggleModal2">
    <h1>{{header}}</h1>
    <p>{{text}}</p>
  </Modal>
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
      title: 'Welcome to the Inc',
      header: 'Sign Up To Continue',
      text: 'You are one step away from being part of this great journey',
      showModal: false,
      showModal2: false,
    }
  },
  methods: {
    toggleModal() {
    this.showModal = !this.showModal
    },

    toggleModal2(){
      this.showModal2 = !this.showModal2
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

button{
  margin-left: 10px;
}
</style>
