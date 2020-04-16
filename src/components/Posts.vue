<template>
<div class="container">
    <h3>Posts:</h3>
    <table class="table">
        <thead>
            <tr>
                <th scope="col">Id</th>
                <th scope="col">Title</th>
                <th scope="col">Body</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="post in posts" v-bind:key="post.id">
                <th scope="row">{{ post.id }}</th>
                <td> {{ post.title }}</td>
                <td> {{ post.body }}</td>
            </tr>
        </tbody>
    </table>
</div>
</template>

<script>
    import axios from 'axios';
    export default {
        name: 'Posts',
        data() {
            return {
                posts: null,
            };
         },

        created: function() {
            axios
            .get('https://jsonplaceholder.typicode.com/posts')
            .then(res => {
                this.posts = res.data;
            })
        }
    }

</script>

<style>
        h3 {
        margin-bottom:5%;
        }
</style>