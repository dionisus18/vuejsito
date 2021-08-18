<template>
  <div>
    <h1>Create an Event, {{ user.name }}</h1>
    <p>This event was created by {{ user.id }}</p>
    <p>{{ getEventById(1) }}</p>
    <ul>
      <li v-for="category in categories" :key="category">{{ category }}</li>
    </ul>
  </div>
</template>

<script>
import { mapState, mapGetters } from 'vuex'
export default {
  computed: {
    getEvent() {
      return this.$store.getters.getEventById
    },
    ...mapState(['user', 'categories']),
    ...mapGetters(['getEventById']),
  },
  /*{ named state
    //userName: (state) => state.user.name, dot notation
    user: 'user', //string notation
    categories: 'categories',
    }*/
}
</script>

<style scoped></style>
