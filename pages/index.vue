<template>
  <div>
    <h1 class="title">Examples</h1>
    <nuxt-link :to="'/examples/example1'" no-prefetch>
      <p>Example 1 - default</p>
    </nuxt-link>
    <nuxt-link :to="'/examples/example2'" no-prefetch>
      <p>Example 2 - lazy load</p>
    </nuxt-link>
  </div>
</template>
<script>
import { mapState } from 'vuex' // <--- To map event

export default {
  components: {},
  // async fetch({ store, error }) {
  //   try {
  //     await store.dispatch('events/fetchEvents')
  //   } catch (e) {
  //     error({
  //       statusCode: 503,
  //       message: 'Unable to fetch events events at this time',
  //     })
  //   }
  // },
  // head() {
  //   return {
  //     title: 'Event Listing',
  //   }
  // },
  computed: mapState({
    events: (state) => state.events.events,
  }),
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
h1.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
