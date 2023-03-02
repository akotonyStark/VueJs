<template>
    <div>
        <hr/>
        <h3>Create Post</h3>
        <form @submit.prevent="createPost">
            <div>
                <label for="userId">Post User ID:</label>
                <input type="text" id="userId" v-model="formData.userId"/>
            </div>
            <div>
                <label for="userId">Post Title:</label>
                <input type="text" id="title" v-model="formData.title"/>
            </div>
            <div>
                <label for="userId">Post Body:</label>
                <textarea type="text" id="body" v-model="formData.body"></textarea>
            </div>
            <button>Submit Post</button>
        </form><br/>
        <button @click="getPosts()">Load Posts from API</button><br/>
        <span v-if="errorMessage">{{ errorMessage }}</span>
        <div v-for="post in posts" :key="post.id">{{ post?.title }}</div>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    name:'LoadPosts',
    data(){
        return {
            posts: [],
            errorMessage: '',
            formData:{
                userId:'',
                title:'',
                body:''
            }
        }
    },
    methods:{
        getPosts(){
            axios.get('https://jsonplaceholder.typicode.com/posts')
            .then((res) => this.posts = res.data)
            .catch((error) => {
                this.errorMessage = error
            })
        },
        createPost(){
            axios.post(`https://jsonplaceholder.typicode.com/posts`, this.formData)
            .then((res) => console.log(res.data))
            .catch((error) => {
                this.errorMessage = error
            })
        }
    },
    //created lifecycle is the best place to make api calls
    created(){
        this.getPosts()
    }
}
</script>
<style lang="">
    
</style>