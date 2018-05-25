<template>
  <div> 
    <div>
    <nuxt-link to="/about">About</nuxt-link>
    </div>
    <div>
      <button @click="gotoAbout">ABout</button>
    </div>
    <v-card>
        <v-container fluid grid-list-md>
          <v-layout row wrap>
            <v-flex
              v-for="card in cards"
              v-bind="{ [`xs${card.flex}`]: true }"
              :key="card.title"
            >
              <v-card>
                <v-card-media
                  :src="card.src"
                  height="200px"
                >
                  <v-container fill-height fluid>
                    <v-layout fill-height>
                      <v-flex xs12 align-end flexbox>
                        <span class="headline back--text" v-text="card.title"></span>
                      </v-flex>
                    </v-layout>
                  </v-container>
                </v-card-media>
                <v-card-actions>
                  <v-spacer></v-spacer>
                  <v-btn icon>
                   <v-btn color="error" class="center">Info</v-btn>
                  </v-btn>                  
                </v-card-actions>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </v-card>
  </div>
  
</template>
<script>
export default {
   data: () => ({
      cards: [
        { title: 'Pre-fab homes', src:'/images/cards/bye.jpg', flex: 12  },
        { title: 'Favorite road trips', src: '/images/cards/road.jpg', flex: 6},
        { title: 'Best airlines', src: '/images/cards/plane.jpg', flex: 6 }
      ]
    }),
  methods:{
    gotoAbout(){
      this.$router.replace('/about')
     this.$router.go(-1)
    },
  },
}
</script>
