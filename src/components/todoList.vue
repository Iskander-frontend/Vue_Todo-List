<template>
    <ul class="posts">
        <li class="post" v-for="(post, index) in posts">
            <p class="title">{{post.title}}</p>
            <p class="body">{{post.body}}</p>
        </li>
    </ul>
</template>

<script>
    export default {
        name: "todoList",
        props: {
            posts: {
                type: Array,
                required: true
            }
        }
    }
</script>

<style lang="scss">
    .posts{
        display: flex;
        flex-direction: column;
        gap: 30px;
    }
    .post{
        display: flex;
        flex-direction: column;
        gap: 20px;
        border: 1px solid teal;
        padding: 10px 20px;
    }
</style>

