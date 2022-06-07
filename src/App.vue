<template>
  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <Modal :header="header" :text="text" :theme="theme" @close="toggleModal" />
  </div>
  <button class="toggle_modal" @click.alt="toggleModal">
    Show Modal (alt)
  </button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My first Vue App :)",
      header: "Header prop data from app vue",
      text: "Modal content from app vue via props",
      theme: "sale",
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
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
