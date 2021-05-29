<template>
<div class="container mt-5">
  <div v-for="article in articles" :key="article.id"> 
    <h3>{{article.body}}</h3>
    <h3>{{article.date}}</h3>
  </div>
</div>

</template>

<script>
export default {

  data() {
    return {
      articles:[]
    }
  },  
  methods: {
    getArticles(){
      fetch("http://localhost:5000/get",{
        method:"GET",
        headers:{
          "Content-Type": "application/json"
        }
      })
      .then(response => response.json())
      .then(data => {
        this.articles.push(...data)
      })
      .catch(err => console.log(err))
    }

  },
    created(){
    this.getArticles()
    }

}
</script>

<style>

</style>