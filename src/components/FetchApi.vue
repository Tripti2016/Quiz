<template >
    <div class="fetch-class">
        <h1>Phone list</h1>
        <table>
            <tr>
                <th>Name</th>
                <th>Airlinn Name</th>
                <th>Country Name</th>
                <th>Totle Trips</th>
                <th>Website</th>
            </tr>
            <tbody>
                <tr v-for="post in posts" :key="post.id">
                    <td>{{ post.name }}</td>
                    <td>{{ post.airline.map((p) => p.name) }}</td>
                    <td>{{ post.airline.map((p) => p.country) }}</td>
                    <!-- <td class="img"><img :src=post.url alt="main-img"></td> -->
                    <td>{{ post.trips }}</td>
                    <td class="thumbnail">{{ post.airline.map((p) => p.website) }} </td>
                </tr>
            </tbody>
        </table>



    </div>
</template>
<script>
import axios from 'axios';


export default {
    name: 'FetchApi',

    data() {
        return {
            posts: [],

        };
    },
    created() {
        axios
            .get('https://api.instantwebtools.net/v1/passenger?page=0&size=40')
            .then((resp) => {
               
                this.posts = resp.data.data;

            })
            .catch(error => {
                console.log(error);
            });
    },

}






</script>
