<script>
import NavBar from './components/MyModal.vue'
import Banana from './components/DarkMode.vue'
import EditTab from './components/EditShop.vue'

export default {
  components: { NavBar, Banana, EditTab },
  name: 'App',
  data() {
    return {
      title: 'My First Vue App :)',
      header: 'sign up for the Giveaway!',
      text: 'Grab your ninja sprite for half price.',
      showModal: false,
      showList: false,
      showEdit: false
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleList() {
      this.showList = !this.showList
    },
    toggleEdit() {
      this.showEdit = !this.showEdit
    }
  }
}
</script>

<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <NavBar theme="dark" @close="toggleModal">
      <h1>Ninja Giveaway!</h1>
      <p>Grab your ninja swag for half price!</p>
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
    </NavBar>
  </div>
  <button @click="toggleModal">open modal</button>

  <button type="button" class="showBanana" @click="toggleList">
    <span v-if="showList" type="">hide shop</span>
    <span v-else>show shop</span>
  </button>

  <div v-if="showList" class="bananao">
    <Banana></Banana>
    <div v-if="showEdit" class="editao">
      <EditTab @closeEdit="toggleEdit"></EditTab>
    </div>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Arial, Helvetica, sans-serif;
  -webkit-font-smoothing: antialised;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

button {
  margin: 0 1rem;
  align-items: center;
  justify-content: center;
  padding: 1rem 1rem;
  border: none;
  border-bottom: 0.2rem solid #e85281;
  background: #2c3e50;
  color: white;
  border-radius: 0.5rem;
  outline: none;
  cursor: pointer;
  overflow: hidden;
  text-align: center;
  transition: 0.25s ease all;
  font-family: 'Roboto', sans-serif;
  font-weight: 500;
  font-style: normal;
  font-size: 22px;
}

button:hover {
  background: #1e2b38;
}
button:focus:active {
  transform: perspective(0.1rem) scale3d(0.98, 0.98, 1) translate3d(0, 0.2rem, 0);
  background-color: #1e2b38;
  border-bottom: 0.2rem solid transparent;
}

li {
  list-style: none;
}

.bananao {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 5px;
  padding: 5px auto;
}
</style>
