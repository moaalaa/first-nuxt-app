<template>
    <div>
        <h1 v-text="error.statusCode"></h1>
        <p v-text="error.message"></p>
    </div>
</template>

<script>
export default {
    props: ['error']
}
</script>
