<template>
  <div id="app">
    <h1>Hotel Booking!</h1>
    <booking-form/>
    <booking-list :bookings="bookings"/>
  </div>
</template>

<script>
import {eventBus} from './main.js';
import BookingForm from './components/BookingForm.vue';
import BookingList from './components/BookingList.vue';
import BookingService from './services/BookingService.js';

export default {
  name: 'App',
  components: {
    'booking-form': BookingForm,
    'booking-list': BookingList
  },
  data() {
    return {
      bookings: []
    };
  },

  mounted() {
    this.fetchBookings();


  },

  methods: {
    fetchBookings() {
      BookingService.getBookings()
      .then(bookings => this.bookings = bookings);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

o