<template>
    <div>
        <post :post="post"></post>
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
            post: {}
        };
    },
    async asyncData({ params }) {
        console.log(params);
        
        let res = await axios.get(`https://jsonplaceholder.typicode.com/posts/${params.id}`);
        
        return { 
            post: res.data
        };
    },
}
</script>
