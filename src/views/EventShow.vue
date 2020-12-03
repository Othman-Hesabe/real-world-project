<template>
  <h1>Showing Event {{ event.title }}</h1>
</template>

<script>
import EvenService from '@/services/EventService.js'
export default {
  props: ['id'],
  data() {
    return {
      event: {}
    }
  },
  create() {
    EvenService.getEvent(this.id)
      .then(response => {
        this.event = response.data
      })
      .catch(error => {
        console.log('There was an error:', error.response)
      })
  }
}
</script>
