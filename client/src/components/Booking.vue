<template>
  <section>
      <h2>Name:{{booking.name}}</h2>
      <p>Email:{{booking.email}}</p>
      <p>Checked in? {{booking.checked_in}}</p>
      
      <button>Delete Booking</button>
  </section>
</template>

<script>
import {eventBus} from '../main.js'


export default {
  name: 'booking',
  props: ['booking'],
  methods: {},
}

</script>

<style>

</style>