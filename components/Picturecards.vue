<template>
  <v-container grid-list-md text-xs-center>
    <v-layout>
      <v-flex v-for="(picture, index) in pictures" :key="index">
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
export default {
  data: function() {
    return {
      pictures: [
        'https://images.dog.ceo/breeds/pekinese/n02086079_5125.jpg',
        'https://images.dog.ceo/breeds/pyrenees/n02111500_1170.jpg',
        'https://images.dog.ceo/breeds/clumber/n02101556_8168.jpg',
        'https://images.dog.ceo/breeds/pomeranian/n02112018_3504.jpg',
        'https://images.dog.ceo/breeds/airedale/n02096051_3981.jpg',
        'https://images.dog.ceo/breeds/rottweiler/n02106550_148.jpg',
        'https://images.dog.ceo/breeds/leonberg/n02111129_819.jpg',
        'https://images.dog.ceo/breeds/schipperke/n02104365_675.jpg',
        'https://images.dog.ceo/breeds/dalmatian/cooper2.jpg'
      ]
    }
  }
}
</script>
