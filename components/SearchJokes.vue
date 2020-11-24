<template>
<form @submit.prevent="onSubmit">
  <input type="text" name="search" v-model="keyword" placeholder="Search Jokes">
  <input type="submit" value="Submit">
  </form>
</template>

<script>
export default {
    name:"SearchJokes",
    data(){
        return{
            keyword:""
        }
    },
    methods:{
        onSubmit(){
            this.$emit("search-keyword",this.keyword)
            this.keyword=""
        }
    }
}
</script>

<style>

</style>