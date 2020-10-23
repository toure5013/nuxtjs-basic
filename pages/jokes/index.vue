<template>
<div class="container-fluid">
    <div>
        <SearchJoke v-on:search-text="searchText" />
    </div>
    <div>
        <v-progress-circular class="container" :size="100" :width="10" color="amber" indeterminate v-if="isLoading"></v-progress-circular>
        <Joke v-for="joke in jokes" :key="joke.id" index="2" :id="joke.id" :joke="joke.joke" v-else />
    </div>
</div>
</template>

<script>
import axios from 'axios';
import Joke from "../../components/Joke";
import SearchJoke from "../../components/SearchJoke";

export default {
    components: {
        Joke,
        SearchJoke
    },
    data() {
        return {
            title: "Dad Jokes",
            baseUrl: 'https://icanhazdadjoke.com',
            jokes: [],
            isLoading: true,

        }
    },
    async created() {
        const config = {
            headers: {
                'Accept': 'application/json'
            }
        }
        try {
            const res = await axios.get(`${this.baseUrl}/search`, config);
            console.log(res.data);
            this.jokes = res.data.results;
            this.isLoading = false;
        } catch (e) {
            console.log(e.message)
        }
    },
    head() {
        return {
            title: this.title,
            meta: [{
                hid: "description",
                name: "description",
                content: "Best place for corny dad jokes"
            }]
        }
    },
    methods: {
        async searchText(text) {
            console.log(text)
            const config = {
                headers: {
                    'Accept': 'application/json'
                }
            }
            try {
                this.isLoading = true;
                const res = await axios.get(`${this.baseUrl}/search?term=${text}`, config);
                this.jokes = res.data.results;
                this.isLoading = false;

            } catch (e) {
                console.log(e.message)
            }
        }

    }
}
</script>

<style>
.container {
    margin: 0 auto;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    color: yellowgreen;
}
</style>
