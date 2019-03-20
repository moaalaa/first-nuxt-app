<template>
    <div class="post">
        <h2 class="post__title">
            <nuxt-link :to="{name: 'posts-id', params: {id: post.id} }" v-text="post.title"></nuxt-link>
        </h2>

        <p v-text="post.body"></p>
    </div>
</template>

<script>
export default {
    props: {
        post: Object,
    }
}
</script>

<style lang="scss">
    .post {
        margin-bottom: 40px;
    }
</style>

