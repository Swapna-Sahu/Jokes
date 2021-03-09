<template>
    <div>
        <SearchJokes v-on:search-text="searchText"/>
        <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke"
        />
    </div>
</template>
<script>
import axios from "axios";
import Joke from '../../components/joke.vue';
import SearchJokes from '../../components/SearchJokes';
export default {
    components:{
        Joke,
        SearchJokes,
    },
    data() {
        return {
            jokes:[]
        };
    },
    async created() {
        const config = {
            headers: {
                'Accept' : 'application/json'
            }
        }
        try {
            const res = await axios.get("https://icanhazdadjoke.com/search", config);
            this.jokes = res.data.results;
            console.log(this.jokes);
        } catch (err) {
            console.log(err);
        }
    },
    methods: {
        async searchText(text) {
            const config = {
            headers: {
                'Accept' : 'application/json'
            }
        }
        try {
            const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config);
            this.jokes = res.data.results;
        } catch (err) {
            console.log(err);
        }
        }
    },
    head() {
        return {
            title:'Giggly Jokes',
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

</style>