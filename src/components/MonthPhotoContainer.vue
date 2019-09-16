<template>
  <div>
    <div v-bind:key='monthPhoto.date' v-for='monthPhoto in monthPhotos'>
      <MonthPhoto v-bind:monthPhoto='monthPhoto'/>
    </div>
  </div>
</template>

<script>
import MonthPhoto from './MonthPhoto.vue'

export default {
  name: 'MonthPhotoContainer',
  components: {
    MonthPhoto
  },
  props: ['monthPhotos']
}
</script>

<style scoped>

</style>