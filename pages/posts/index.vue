<template>
    <div>
        <post v-for="post in posts" :key="post.id" :post="post"></post>
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
