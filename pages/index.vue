<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <v-card>
        <v-card-title class="headline">REIgo</v-card-title>
        <v-card-text>
          <v-form ref="form" v-model="valid" lazy-validation>
            <v-text-field
              v-model="arv"
              label="ARV" required
            />
          </v-form>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="primary" flat nuxt to="/inspire">Continue</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import {VForm, VTextField} from 'vuetify'
export default {
  name: 'Home',
  components: {
    VForm,
    VTextField
  },
  data: () => {
    return {
      valid: true,
      arv: 0
    }
  }
}
</script>

