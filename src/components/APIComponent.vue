<template>
    <div>
        <button @click="getPosts()">Load Posts from API</button>
        <div v-for="post in posts" :key="post.id">{{ post?.title }}</div>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    name:'LoadPosts',
    data(){
        return {
            posts: []
        }
    },
    methods:{
        getPosts(){
            axios.get('https://jsonplaceholder.typicode.com/posts')
            .then((res) => this.posts = res.data)
        }
    }
}
</script>
<style lang="">
    
</style>