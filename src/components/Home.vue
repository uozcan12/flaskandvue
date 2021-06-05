<template>
<div class="container mt-5">
  <div v-for="article in articles" :key="article.id"> 
    <h3>
      <router-link :to="{name:'details', params:{id:article.id}}">
        {{article.title}}
      </router-link>
    </h3>
    <p>{{article.body}}</p>
    <p>{{article.date}}</p>
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