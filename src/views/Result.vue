<template>
  <v-container>
    <v-row class="text-center">
      

      <div style="text-align:center">
          <span>"{{$route.params.keyword}}"の検索結果</span>
      </div>
      
                  <v-card
          max-width="400"
          class="mx-auto"
          color="white"
        >
          

          

          <v-container>
            <v-row dense>
              <div style="margin-bottom:10px" v-for="(item, i) in items" :key="i">
                
              <v-col
                cols="12"
              >
                <v-card
                  color="pink"
                  dark
                  :href="item.collectionViewUrl"
                  target="_blank"
                >
                  <div class="d-flex flex-no-wrap justify-space-between">
                    <div>
                      <v-card-title
                        class="headline"
                        v-text="item.collectionName"
                      ></v-card-title>

                      <v-card-subtitle v-text="item.artistName"></v-card-subtitle>
                    </div>

                    <v-avatar
                      class="ma-3"
                      size="125"
                      tile
                    >
                      <v-img :src="item.artworkUrl100"></v-img>
                    </v-avatar>
                  </div>
                </v-card>
                
              </v-col>
              </div>
            </v-row>
          </v-container>
        </v-card>
     
        

     
    </v-row>
  </v-container>
</template>


<script>
import axios from 'axios'
  export default {
    data(){
      return{
        items:[],
      }
    },
    created() {
      const vm=this
      axios.get(`https://itunes.apple.com/search?term=${this.$route.params.keyword}&entity=album`).
      then(response =>{
        console.log(response)
        vm.items = response.data.results
      })
  }
  }
</script>