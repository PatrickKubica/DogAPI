<template>
  <v-container grid-list-md text-xs-center>
    <v-layout wrap>
      <v-flex v-for="(picture, index) in pictures" :key="index" xs4>
        <v-card>
          <v-img
            :src="picture"
            aspect-ratio="2.75"
          />
          <v-card-actions>
            <v-btn :href="picture" flat color="orange">
              Open
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>
<script>
import axios from 'axios'

export default {
  data: function() {
    return {
      pictures: []
    }
  },
  mounted() {
    axios
      .get('https://dog.ceo/api/breeds/image/random/9')
      .then(response => (this.pictures = response.data.message))
  }
}
</script>
