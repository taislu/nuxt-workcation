<template>
  <div id="app">
    <WorkcationTop />

    <div>
      <div class="max-w-md sm:max-w-xl lg:max-w-6xl mx-auto px-8 lg:px-12 py-8">
        <h2 class="text-xl text-indigo-700">Popular Destinations</h2>
        <p class="text-gray-600">
          A selection of great work-friendly cities with lots to see and
          explore.
        </p>
        <div class="flex flex-wrap -mx-4">
          <div
            v-for="destination in popularDestinations"
            :key="destination"
            class="mt-6 w-full px-4 lg:w-1/2 xl:w-1/3"
          >
            <DestinationCard :destination="destination" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'
import DestinationCard from '../components/DestinationCard'
import WorkcationTop from '../components/WorkcationTop'

export default {
  name: 'App',
  components: {
    DestinationCard,
    WorkcationTop
  },
  computed: mapState(['popularDestinations'])
}
</script>

<style>
.btn {
  @apply inline-block px-5 py-3 rounded-lg text-sm uppercase tracking-wider font-semibold;
}

.btn:focus {
  @apply outline-none shadow-outline;
}

.btn-indigo {
  @apply bg-indigo-500 text-white;
}
.btn-indigo:hover {
  @apply bg-indigo-400;
}
.btn-indigo:active {
  @apply bg-indigo-600;
}

.btn-gray {
  @apply bg-gray-400 text-gray-800;
}
.btn-gray:hover {
  @apply bg-gray-300;
}
.btn-gray:active {
  @apply bg-gray-500;
}
</style>
