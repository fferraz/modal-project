<template>
  <h1> {{ title }} </h1>
  <p> Welcome...  </p>
  <teleport to="#modals" v-if="showModal">
    <!-- <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/> -->
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links >
        <a href="#"> sign up now</a>
        <a href="#"> more info </a>
      </template>
      <h1> Giveaway </h1>
      <p> signup! </p>
    </Modal>
  </teleport>

  <teleport to="#modals" v-if="showModalTwo">
    <!-- <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/> -->
    <Modal @close="toggleModalTwo">
      <template v-slot:links >
        <a href="#"> Buy</a>
        <a href="#"> Sell </a>
      </template>
      <h1> Computers </h1>
      <p> Discount! </p>
    </Modal>
  </teleport>
  <button @click="toggleModal"> Open modal </button>
  <p> <button @click="toggleModalTwo"> Open modal 2 </button> </p>

  <!-- <input type="text" ref="name">
  <button @click="handleClick"> click me</button> -->
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',
  components: {
    Modal
  },
  data(){
    return{
      title: 'My Vue app',
      showModal: false,
      showModalTwo: false
      // header: 'Signup for the giveaway',
      // text: 'Grab for free',
    }
  },
  methods:{
    handleClick(){
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo
    }
  }
}
</script>

<style>
#app, #modals{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1 px solid #ddd;
  display: inline-block;
  padding-bottom: 10 px;
}
</style>
