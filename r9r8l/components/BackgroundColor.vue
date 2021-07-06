<template>
  <div
    v-editable="blok">
    bg color
  </div>
</template>

<script>
export default {
  props: {
    blok: {
      type: Object,
      required: true
    }
  }
}
</script>