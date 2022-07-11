<template>
<div class="container">
    <form @click.prevent class="form">
        <h1 class="form__title">Form</h1>
        <input class="input" v-model="title" type="text">
        <input class="input" v-model="body" type="text">
        <button class="btn" @click="addPost">Add</button>
    </form>
    <ul class="posts">
        <li class="post" v-for="(post, index) in posts">
            <p class="title">{{post.title}}</p>
            <p class="body">{{post.body}}</p>
        </li>
    </ul>
</div>
</template>


<script>
    export default {
            data(){
                return {
                posts: [
                    {id: 0, title: "Title One", body: "IOHFGosidghdsfg"},
                    {id: 1, title: "Title Two", body: "ffgjdghjdjfgh"},
                    {id: 2, title: "Title Three", body: "34534tgzxfghd"},
                    {id: 3, title: "Title Four", body: "cvznzfgy4wy4r5"},
                ],
                    title: "",
                    body: ""
            }
        },
        methods: {
            addPost(){
                const newPost = {
                    id: Date.now(),
                    title: this.title,
                    body: this.body
                }
                this.posts.unshift(newPost)
                this.title = ""
                this.body = ""

            }
        }
    }
</script>


<style lang="scss">
    @import "assets/reset.css";

    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
    }
    .container{
        max-width: 1200px;
        margin: 0 auto;
    }
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
    .title{
        font-size: 20px;
        font-weight: 700;
    }
    .body{
        color: #5f5e5e;
    }
    .form{
        display: flex;
        flex-direction: column;
        gap: 30px;
        margin: 50px 0;
    }
    .form__title{
        font-size: 32px;
        font-weight: 700;
    }
    .input{
        padding: 10px 20px;
    }
    .btn{
        display: flex;
        align-self: flex-end;
        padding: 10px 20px;
        border: 1px solid teal;
        background: transparent;
    }

</style>
