<template>
<nuxt-link :to="'jokes/'+ id">
<div class="joke">
<p>{{joke.joke}}</p>

  </div>
</nuxt-link>
  
</template>

<script>

export default {
  components: {
    name: "Joke"
  },
  props:["joke", "id"]
 
 
};
</script>

<style>
.joke {
  padding: 1rem;
  border: 1px dotted #ccc;
  margin: 1rem 0;
}
</style>
