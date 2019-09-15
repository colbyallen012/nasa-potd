<template>
  <div>
    <p>{{photo.explanation}}</p>
  </div>
</template>

<script>

export default {
  name: 'Potd',
  props: {
    photo: String
  }
}
</script>

<style scoped>
  #p {
    font-weight: boldg
  }
</style>