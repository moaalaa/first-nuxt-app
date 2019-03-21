<template>
    <div>
        <post :post="post" :single="true"></post>
    </div> 
</template>

<script>
import axios from 'axios';
import Post from '@/components/Post';

export default {
    layout: 'posts',
    components: {
        Post,
    },
    data() {
        return {
            post: {}
        };
    },
    head() {
        return {
            title: 'Posts | ' + this.post.title,
        };
    },
    async asyncData({ params, error }) {

        console.log(params);
        
        try {
            let res = await axios.get(`https://jsonplaceholder.typicode.com/posts/${params.id}`);
            
            return { 
                post: res.data
            };

        } catch (e) {
            error({
                statusCode: e.response.status,
                message: 'error'
            })
        }
    },
}
</script>
