<template>
  <v-layout row justify-center align-center>
    <v-flex xs12>
      <v-card>
        <v-card-text>
          <v-form ref="form" v-model="valid" lazy-validation>
            <v-text-field prefix="$"
              v-model.number="arv"
              label="Full Market Value" required
            />
            <v-text-field prefix="$"
              v-model="purchasePrice"
              label="Purchase Price"  
            />
            <v-text-field
              v-model="address"
              label="Address"
            />
             <v-text-field
              v-model="year"
              label="Year Built"  
            />
            <v-text-field
              v-model="sqft"
              label="Square Footage"  
            />
          </v-form>
        </v-card-text>
        <v-card-actions>
          <v-card-title class="headline">
            <v-rating
              v-model="rating"
              readonly
              half-increments
              background-color="orange lighten-3"
              color="orange"
              medium
            ></v-rating>
          </v-card-title>
          <v-spacer></v-spacer>
          <v-btn v-if="!isLoading" 
            color="primary"
            v-on:click="run" 
          >Run the numbers</v-btn>
          <v-progress-circular
            v-if="isLoading"
            indeterminate
            color="primary"
          ></v-progress-circular>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import {VForm, VTextField, VRating, VProgressCircular} from 'vuetify'
export default {
  name: 'Home',
  components: {
    VForm,
    VTextField,
    VRating,
    VProgressCircular
  },
  data: () => {
    return {
      valid: true,
      arv: null,
      address: null,
      sqft: null,
      year: null,
      purchasePrice: null,
      rating: 0,
      isLoading: false
    }
  },
  methods: {
    run () {
      this.isLoading = true
      setTimeout(() => {
        this.isLoading = false
        this.rating = Math.floor(Math.random() * (10 - 1))
      }, 2000)
    }
  }
}
</script>

