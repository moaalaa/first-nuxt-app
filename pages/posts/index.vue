<template>
    <div>
        <post v-for="post in posts" :key="post.id" :post="post" :single="false"></post>

        <a href="#" v-scroll-to="'body'">To Top</a>
    </div>
</template>

<script>
import axios from 'axios';
import Post from '@/components/Post';

export default {
    components: {
        Post,
    },
    data() {
        return {
            posts: []
        };
    },
    head: {
        title: 'Posts'
    },
    // asyncData() {
    //     return axios.get('https://jsonplaceholder.typicode.com/posts').then(({data}) => {
    //         return { 
    //             posts: data
    //         };
    //     })  
    // },
    async asyncData() {
        let res = await axios.get('https://jsonplaceholder.typicode.com/posts');
        
        return { 
            posts: res.data
        };
    },
    
    // asyncData() {
        
    // },
}
</script>
