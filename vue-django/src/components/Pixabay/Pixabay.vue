<template>
  <b-container fluid class="p-4 bg-dark text-white">
    <b-row>
<!--      <b-col md="6">
        <b-form-input v-model="buscar" placeholder="Search" @keypress.enter="searchImages"></b-form-input>
      </b-col>
      <b-col md="1">
        <b-button variant="danger" @click="searchImages">
          Buscar
        </b-button>
      </b-col>-->
      <b-col>
        <Buscador @buscarDesdeHijo="searchImages"/>
      </b-col>
    </b-row>
    <b-row>
      <b-col v-for="image in pixaImages" :key="image.id" md="2" class="py-2 text-center">
        <Imagen :img="image"></Imagen>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import ServicioApi from "./ServicioApi";
import Imagen from "@/components/Pixabay/Imagen";
import Buscador from "@/components/Pixabay/Buscador";

export default {
  name: 'Pixabay',
  components: {
    Imagen,
    Buscador
  },
  data() {
    return {
      pixaImages: [],
      buscar: ""
    }
  },
  methods: {
    async searchImages(buscar = "") {
      this.buscar = buscar;
      const consulta = await ServicioApi.getImages(this.buscar)
      this.pixaImages = consulta.hits
    }
  },
  mounted() {
    this.searchImages()
  }
};
</script>
<style>

</style>
