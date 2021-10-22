<template>
  <div>
    <b-img :src="img.previewURL" thumbnail fluid v-b-popover.hover.top="img.tags" :title="img.tags"></b-img>
  </div>
</template>

<script>
export default {
  name: "Imagen",
  props: ["img"]
}
</script>

<style scoped>

</style>