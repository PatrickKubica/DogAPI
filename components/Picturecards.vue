<template>
  <v-container grid-list-md text-xs-center>
    <v-btn flat color="orange" @click="getRandomImages">
      Get fresh dog pictures!
    </v-btn>
    <v-layout wrap>
      <v-flex v-for="(picture, index) in pictures" :key="index" xs6 md4>
        <v-card>
          <v-img
            :src="picture"
            aspect-ratio="1.5"
            @click="openImage(picture)"
          />
          <v-card-actions>
            <v-btn :href="picture" flat color="orange">
              open
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
      .get('https://dog.ceo/api/breeds/image/random/6')
      .then(response => (this.pictures = response.data.message))
  },
  methods: {
    getRandomImages() {
      axios
        .get('https://dog.ceo/api/breeds/image/random/6')
        .then(response => (this.pictures = response.data.message))
    },
    openImage(picture) {
      window.open(picture, '_self')
    }
  }
}
</script>
