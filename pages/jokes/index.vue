<template>
<div class="container-fluid">
    <Joke v-for="joke in jokes" :key="joke.id" index="2" :id="joke.id" :joke="joke.joke" />
</div>
</template>

<script>
import axios from 'axios';
import Joke from "../../components/Joke";

export default {
    components: {
        Joke,
    },
    data() {
        return {
            title: "Dad Jokes",
            baseUrl: 'https://icanhazdadjoke.com',
            jokes: []
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
    }
}
</script>
