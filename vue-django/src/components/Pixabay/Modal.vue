<template>
  <div>
    <b-modal v-model="mostrar" hide-footer size="x1" :title="img.tags">
      <div class="d-block text-center">
        <b-img-lazy top :id="img.id" :src="img.largeImageURL" :alt="img.tags" fluid rounded
                    v-b-popover.focus="img.tags"/>
      </div>
    </b-modal>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props: ["img", "mostrarModal"],
  computed: {
    mostrar: {
      get() {
        return this.mostrarModal
      },
      set(valor) {
        return valor
      }
    }
  }
}
</script>

<style scoped>

</style>