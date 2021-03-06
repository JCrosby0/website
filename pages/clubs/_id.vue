<template>
  <div>
    <!-- // Link to go back to the previous page -->
    <a class="uk-button uk-button-primary uk-margin" @click="$router.go(-1)"
      ><span uk-icon="arrow-left"></span> go back</a
    >

    <client-only>
      <div uk-grid>
        here's more informatoin about the club
        {{ Object.values(club) }}
        <!-- // Left card displaying dishes -->
        <div class="uk-width-1-3@m">
          <!-- <div v-for="dish in restaurant.dishes" class="uk-margin">
            <div class="uk-card uk-card-default">
              <div class="uk-card-media-top">
                <img :src="'http://localhost:1337/' + dish.image.url" alt="" />
              </div>
              <div class="uk-card-body">
                <h3 class="uk-card-title">
                  {{ dish.name }}
                  <span class="uk-badge">{{ dish.price }}€</span>
                </h3>
                <p>{{ dish.description }}</p>
              </div>
              <div class="uk-card-footer">
                // Doing nothing for the moment :)
                <button class="uk-button uk-button-primary">Add to cart</button>
              </div>
            </div>
          </div> -->
        </div>

        // Right card that will display your cart
        <div class="uk-width-expand@m"></div>
      </div>
    </client-only>
  </div>
</template>

<script>
import clubQuery from '~/apollo/queries/club/club'

export default {
  data() {
    return {
      club: Object,
    }
  },
  apollo: {
    club: {
      prefetch: true,
      query: clubQuery,
      variables() {
        return { id: this.$route.params.id }
      },
    },
  },
}
</script>
