<template>
  <div>
    <b-img :src="img.previewURL" thumbnail fluid v-b-popover.hover.top="img.tags" :title="img.tags"
           @click="showModal"></b-img>
    <Modal :mostrarModal="mostrarModal" :img="img"/>
  </div>
</template>

<script>
import Modal from "@/components/Pixabay/Modal";

export default {
  name: "Imagen",
  props: ["img"],
  components: {
    Modal
  },
  data() {
    return {
      mostrarModal: false
    }
  },
  methods: {
    showModal() {
      this.mostrarModal = true;
    }
  }, mounted() {
    this.$root.$on('bv::modal::hide', () => {
      this.mostrarModal = false
    })
  }
}
</script>

<style scoped>

</style>