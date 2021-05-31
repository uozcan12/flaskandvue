<template>
    <div class="container mt-5">
        <h2>{{article.title}}</h2>
        <p class="mt-3">
            {{article.body}}
        </p>
        <h6>Published Date: {{article.title}}</h6>
    </div>  
</template>

<script>
export default {
    data(){
        return {
            article:{}
        } 
    },
    props:{
        id :{
            type:[Number, String],
            required:true
        }
    },
    methods:{
        getArticleData(){
            fetch(`http://localhost:5000/get/${this.id}/`,{
                method:"GET",
                headers:{
                    "Content-Type": "application/json"
                }
            })
            .then(response => response.json())
            .then(data => {
                this.articles = data
            })
            .catch(err => console.log(err))
        }
    },
    created(){
        this.getArticleData()
    }
}
</script>

<style>

</style>