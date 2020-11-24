<template>
  <div>
      <h3>About DadJokes</h3>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Modi, saepe fugiat. Doloribus, blanditiis laborum? Id neque expedita blanditiis sed adipisci!</p>
  </div>
</template>

<script>
export default {
    // this adds a title to our head tag of the page >>check tab  in browser
    head(){
        return{
            title: "About the App",
            meta: [
                {
                    hid:"description",
                    name:"description",
                    content:"Best place for dad jokes"
                }
            ]
        }

    }

}
</script>

<style scoped>

</style>