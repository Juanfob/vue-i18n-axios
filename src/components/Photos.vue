<template>
<div class="container">
    <h3>Photos:</h3>
    <table class="table">
        <thead>
            <tr>
                <th scope="col">Id</th>
                <th scope="col">Title</th>
                <th scope="col">Image</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="photo in photos" v-bind:key="photo.id">
                <th scope="row">{{ photo.id }}</th>
                <td> {{ photo.title }}</td>
                <td> {{ photo.thumbnailUrl  }}></td>
            </tr>
        </tbody>
    </table>
</div>
</template>

<script>
    import axios from 'axios';
    export default {
        name: 'Photos',
        data() {
            return {
                photos: null,
            };
         },

        created: function() {
            axios
            .get('https://jsonplaceholder.typicode.com/photos')
            .then(res => {
                this.photos = res.data;
            })
        }
    }

</script>

<style>
        h3 {
        margin-bottom:5%;
        }
</style>