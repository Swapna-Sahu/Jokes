<template>
    <div>
        <nuxt-link to="/jokes" class="back-btn">
        Back to Jokes
        </nuxt-link>

        <h2>{{joke}}</h2>
        
        <img src="../../../assets/gigglyJoke.png" class="image" alt="joke image"/>
        <hr>
        <small> Joke Id : {{$route.params.id}}</small>
    </div>
</template>
<script>
import axios from 'axios';

export default {
    data() {
        return {
            joke:{}
        }
    },
    async created() {
        const config = {
            headers: {
                'Accept' : 'application/json'
            }
        }
        try {
            const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config);
            this.joke = res.data.joke;
            console.log(this.joke);
        } catch (err) {
            console.log(err);
        }
    },
    head() {
        return {
            title:this.joke,
            meta: [
                {
                    hid: 'decription',
                    name: 'description',
                    content: 'Best places for the jokes'
                }
            ]
        }
    },
}
</script>
<style>
.back-btn {
    background-color: rgb(73, 72, 72);
    color: blanchedalmond;
    padding: 8px;
}
h2{
    margin: 30px 0 30px 0;
}
</style>