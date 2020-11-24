<template>
  <div>
      <SearchJokes v-on:search-keyword="search"/>
     <Joke v-for="joke in jokes" :key="joke.id" :joke="joke" :id="joke.id"/>
  </div>
</template>

<script>
import Joke from '../../components/Joke.vue'
import SearchJokes from '../../components/SearchJokes.vue'
import axios from "axios"
export default {
    components:{
        Joke,
         SearchJokes
    },
        head(){
        return{
            title: "Jokes",
            meta: [
                {
                    hid:"description",
                    name:"description",
                    content:"Best place for dad jokes"
                }
            ]
        }

    },
     data() {
         return{
        jokes: []
         }
   
  },
  created() {
    this.fetchJokes();
  },
  methods: {
    async fetchJokes() {
      let config = {
        headers: {
          Accept: "application/json"
        }
      };
      try {
        let res = await axios.get("https://icanhazdadjoke.com/search", config);
       this.jokes = res.data.results
       console.log("here", this.jokes)
      } catch (error) {
        console.log(error);
      }
    },
    async search(keyword){
             let config = {
        headers: {
          Accept: "application/json"
        }
      };
      try {
              let res = await axios.get(`https://icanhazdadjoke.com/search?term=${keyword}`, config);
       this.jokes = res.data.results
          
      } catch (error) {
          console.log(error)
          
      }

    }
  }

}
</script>

<style>

</style>