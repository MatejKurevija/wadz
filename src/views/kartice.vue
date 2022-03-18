<template>
      <v-container  v-if = "commit.commit">
      <v-card>
                   
              <v-card-text><strong>{{shaID}}</strong></v-card-text>

              <v-card-text>{{ commit.commit.author.name }}</v-card-text>

              <v-card-text>{{ commit.commit.author.email }}</v-card-text>

              <v-card-text>{{ commit.commit.message }}</v-card-text>

              <v-card-text>{{ commit.commit.author.date }}</v-card-text>
              
         <v-btn @click="HomeFun" style="margin: 1rem 1rem;">Nazad</v-btn>
      </v-card>

      
      </v-container>



</template>

<script>
import axios from 'axios'

export default {
name: 'kartice',
data(){
    return{
      shaID: this.$route.params.shaID,
      commit: [],
    }
  },
  async mounted(){
    const neka = await axios.get(`https://api.github.com/repos/vuejs/vue/commits/${this.shaID}`)
    this.commit = neka.data
 
  },
    methods:{
        HomeFun(){
            this.$router.push('/')
        }
    }
}

</script>

<style>

</style>