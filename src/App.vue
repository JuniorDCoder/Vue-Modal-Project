<template>
  <h1>{{ title }}</h1>
  <p>Welcome ...</p>
  <teleport to=".modals" v-if="isClicked">
    <Modal theme="sale" @close="ToggleClick">
      <template v-slot:links>
        <a href="">SignUp Now</a>
        
        <a href="">More Info</a>
      </template>
      <h1>Ninga Giveaway!</h1>
      <p>Grab your ninga swag for half the actual price!</p>
    </Modal>
  </teleport>
  <teleport to=".modals" v-if="isClicked2">
    <Modal @close="ToggleClick2">
      <h1>Sign Up to Newsletter!</h1>
      <p>For Updates and Promo Codes!</p>
    </Modal>
  </teleport>
  <button @click="ToggleClick">Open Modal</button> 
  <button @click="ToggleClick2">Open Modal Two</button> 
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  data(){
    return {
      title: "My First Vue App :)",
      isClicked: false,
      isClicked2: false,
      header: "50% off Everything!",
      text: "Grab Your Ninga Sweater for half the price!"
    }
  },
  methods: {
    ToggleClick(){
      this.isClicked = !this.isClicked
    },
    ToggleClick2(){
      this.isClicked2 = !this.isClicked2
    }
  }
}
</script>

<style>
#app, .modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
