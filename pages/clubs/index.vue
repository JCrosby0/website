<template>
  <div>
    <!-- // Search input to filters      -->
    <form class="uk-search uk-search-large uk-align-center uk-margin">
      <span uk-search-icon></span>
      <input
        v-model="query"
        class="uk-search-input"
        type="search"
        placeholder="Search..."
      />
    </form>

    <!-- // Club cards -->
    <div
      v-for="(club, i) in filteredList"
      :key="'club-' + i"
      class="uk-card uk-card-default uk-grid-collapse uk-child-width-1-2@m uk-margin"
      uk-grid
    >
      <div class="uk-card-media-left uk-cover-container">
        <img
          :src="'http://localhost:1337' + club.img[0].url"
          :alt="`${club.name} logo`"
          uk-cover
        />
        <!-- <canvas width="600" height="400"></canvas> -->
      </div>
      <div>
        <div class="uk-card-body">
          <h3 class="uk-card-title">{{ club.name }}</h3>
          <p>{{ club.suburb }}</p>
          <p>{{ club.description }}</p>
          <!-- // Link to the club using router-link -->
          <router-link
            :to="{ name: 'clubs-id', params: { id: club.id } }"
            tag="a"
            class="uk-button uk-button-primary"
            >Click here to see details
          </router-link>
          or
          <a :href="club.website" target="_blank">visit the club's website</a>
        </div>
      </div>
    </div>

    <!-- // If no clubs have been found -->
    <div
      v-if="filteredList.length == 0"
      class="uk-container uk-container-center uk-text-center"
    >
      <img
        src="https://assets-ouch.icons8.com/preview/19/52de2377-696e-4194-8c63-0a81aef60b4f.png"
        height="800"
        width="800"
      />
      <p>No clubs found</p>
    </div>
  </div>
</template>

<script>
// Import the clubs query
import clubsQuery from '@/apollo/queries/club/clubs'

export default {
  data() {
    return {
      // Initialize an empty clubs variable
      clubs: [],
      query: '',
    }
  },
  apollo: {
    clubs: {
      prefetch: true,
      query: clubsQuery,
    },
  },
  computed: {
    // Search system
    filteredList() {
      return this.clubs.filter((club) => {
        return club.name.toLowerCase().includes(this.query.toLowerCase())
      })
    },
  },
}
</script>
