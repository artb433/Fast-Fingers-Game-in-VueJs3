<template>
<div><h1>{{title}}</h1></div>
<button @click="toggleModal">Sign Up</button>
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
<div>
  <button @click="start" :disabled="isPlaying">Play</button>
</div>

<Block v-if="isPlaying" :delay="delay" @end="endGame"/>
<Results v-if="showResults" :score="score"/>
<p v-if="showResults">Reaction Time:{{score}} ms</p>



</template>
    
<script>
import Modal from './components/Modal.vue'
import Block from './components/Block.vue'
import Results from './components/Results.vue'


export default {
  name: 'App',
  components: {
    Modal,
    Block,
    Results
  },
  data() {
    return {
      title: 'Welcome to Fast Fingers',
      header: 'Sign Up To Continue',
      text: 'You are one step away from being part of this great journey',
      showModal: false,
      showModal2: false,
      isPlaying: false,
      delay:null,
      score: null,
      showResults: false
    }
  },
  methods: {
    toggleModal() {
    this.showModal = !this.showModal
    },

    toggleModal2(){
      this.showModal2 = !this.showModal2
    },

    start() {
      this.isPlaying = true
      this.delay= 2000 + Math.random() * 5000
      this.showResults = false
      // this.delay = setTimeout(() => {
      //   this.isPlaying = false
      // }, 2000 + Math.random() * 5000),
      console.log(this.delay)
    },
    endGame(reactionTime){
      this.isPlaying = false
      this.score = reactionTime
      this.showResults = true
      console.log(reactionTime)
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
  color: #444;
  margin-top: 60px;
} 

h1 {
border-bottom: 1px solid #ddd;
display: inline-block;
padding-bottom: 10px;
color: black;
}

button{
background: #0faf87;
color: white;
border: none;
padding: 8px 16px;
border-radius: 4px;
font-size:16px;
letter-spacing: 1px;
cursor: pointer;
margin: 20px;
}
button[disabled]{
  opacity:0.2;
  cursor: not-allowed;
}

.modal h1 {
  color: #03cfb4;
  border: none;
  padding: 0;
}

.modal p {
  font-style: normal;
}

.modal .actions {
  text-align: center;
  margin: 30px 0 10px 0;
}

.modal .actions a {
  color: #333;
  padding: 8px;
  border: 1px solid #eee;
  border-radius: 4px;
  text-decoration: none;
  margin: 10kpx;
}

.modal .sale {
  background: crimson;
  color: white;;
}

.modal .sale h1 {
  color: white;
}

.modal .sale .actions {
  color: white;
}

.modal .sale .actions a {
  color: white;
}
</style>
