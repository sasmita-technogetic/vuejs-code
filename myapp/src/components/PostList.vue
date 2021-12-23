<template>
    <div>
        <button @click="getPosts">Load posts</button>
        <h3 v-if="errorMsg">{{errorMsg}}</h3>
        <div v-for="post in posts" :key="post.id">
            <h3>{{post.id}}. {{post.title}}</h3>
            <p>{{post.body}}</p>
        </div>
    </div>
</template>
<script>
import axios from 'axios';
export default {
    
    name:'PostList',
    data(){
        return {
            posts: [],
            errorMsg: '',
        }
    },
    methods: {
        getPosts(){
            axios.get('https://jsonplaceholder.typicode.com/posts')
           .then((res)=>{
               this.posts = res.data
               console.log(res.data);
           })
           .catch((err)=>{
               console.log(err)
           this.errorMsg = "Error Retriving data"
           }
           )
        }
    }
}
</script>
