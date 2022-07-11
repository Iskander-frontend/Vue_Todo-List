<template>
    <form @click.prevent class="form">
        <h1 class="form__title">Form</h1>
        <input
                class="input"
                v-model="post.title"
                type="text">
        <input
                class="input"
                v-model="post.body"
                type="text">
        <button
                class="btn"
                @click="createPost">Add</button>
    </form>
</template>

<script>
    export default {
        name: "todoForm",
        data() {
            return {
                post: {
                    title: '',
                    body: ''
                }
            }
        },
        methods: {
            createPost() {
                if (this.post.title.length > 0 && this.post.body.length > 0){
                    this.post.id = Date.now();
                    this.$emit('create', this.post)
                    this.post = {
                        title: '',
                        body: ''
                    }
                }
            }
        },
    }
</script>

<style lang="scss">
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
        cursor: pointer;
    }
</style>