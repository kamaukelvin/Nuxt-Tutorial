<template>
  <div>
      <nuxt-link to="/jokes">Back to Jokes</nuxt-link>
      <h2>{{joke}}</h2>
      <hr>
    <small>Joke ID: {{ $route.params.id }}</small>
  </div>
</template>

<script>
import axios from 'axios'
export default {
    created(){
        this.fetchSingleJoke()
    },
    methods:{
        async fetchSingleJoke(){
            let config = {
        headers: {
          Accept: "application/json"
        }
        }
            try { 
            let resp = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id }`, config)
            this.joke= resp.data.joke
            } catch (error) {

            }
    }
    },
    data(){
        return{
            joke:{}
        }
    },
    // dynamic title of tab
        head(){
        return{
            title: this.$route.params.id,
            meta: [
                {
                    hid:"description",
                    name:"description",
                    content:"Best place for dad jokes"
                }
            ]
        }

    },


}
</script>

<style></style>
