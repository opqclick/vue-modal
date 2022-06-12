<template>
  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <Modal :theme="theme" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">more..</a>
      </template>
      <h1>Asynchronous Giveaway!</h1>
      <p>Grab swag for free :)</p>
    </Modal>
  </div>
  <button class="toggle_modal" @click.alt="toggleModal">
    Show Modal (alt)
  </button>
  <b></b>
  <div v-if="showAnotherModal">
    <AnotherModal :theme="theme" @close="toggleAnotherModal">
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">more..</a>
      </template>
      <h1>Asynchronous Another Giveaway!</h1>
      <p>Grab swag for free :)</p>
    </AnotherModal>
  </div>
  <button class="toggle_modal" @click.shift="toggleAnotherModal">
    Show Another Modal (shift)
  </button>
</template>

<script>
import Modal from "./components/Modal.vue";
import AnotherModal from "./components/AnotherModal.vue";

export default {
  name: "App",
  components: { Modal, AnotherModal },
  data() {
    return {
      title: "My first Vue App :)",
      header: "Header prop data from app vue",
      text: "Modal content from app vue via props",
      theme: "sale",
      showModal: false,
      showAnotherModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleAnotherModal() {
      this.showAnotherModal = !this.showAnotherModal;
    },
  },
};
</script>

<style scope>
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
}
.toggle_modal {
  display: block;
  margin: 10px auto;
}
</style>
