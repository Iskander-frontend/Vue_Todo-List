<template>
<div class="container">
    <todo-form
            @create="createPost"
    />
<todo-list
        :posts="posts"
/>
</div>
</template>


<script>
    import TodoForm from "@/components/todoForm";
    import TodoList from "@/components/todoList";
    export default {
        components: {TodoList, TodoForm},
        data(){
                return {
                posts: [
                    {id: 0, title: "Title One", body: "IOHFGosidghdsfg"},
                    {id: 1, title: "Title Two", body: "ffgjdghjdjfgh"},
                    {id: 2, title: "Title Three", body: "34534tgzxfghd"},
                    {id: 3, title: "Title Four", body: "cvznzfgy4wy4r5"},
                ],
            }
        },
        methods: {
            createPost(post) {
                    this.posts.unshift(post)
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
    .title{
        font-size: 20px;
        font-weight: 700;
    }
    .body{
        color: #5f5e5e;
    }

</style>
