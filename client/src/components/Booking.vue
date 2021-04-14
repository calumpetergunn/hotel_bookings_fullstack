<template>
  <section>
      <h2>Name:{{booking.name}}</h2>
      <p>Email:{{booking.email}}</p>
      <p>Checked in? {{booking.checked_in}}</p>
      
      <button v-on:click="handleDelete(booking._id)">Delete Booking</button>
  </section>
</template>

<script>
import {eventBus} from '../main.js'


export default {
  name: 'booking',
  props: ['booking'],
  methods: {
    handleDelete(id){
      eventBus.$emit('delete-booking', id)
    }
  },
}

</script>

<style scoped>

</style>