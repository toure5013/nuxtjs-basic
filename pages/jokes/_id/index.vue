<template lang="fr">
<div class="videobg">
    <div class="overlay"></div>
    <video playsinline="playsinline" autoplay="autoplay" muted="muted" loop="loop">
        <source src="https://storage.googleapis.com/coverr-main/mp4/Mt_Baker.mp4" type="video/mp4">
    </video>
    <div class="container h-100">
        <div class="d-flex h-100 text-center align-items-center">
            <div class="w-100 text-white">
                <h1 class="text-muted"> {{$route.params.id}}</h1>
                <p class="lead mb-0">
                <p class="text">
                    {{joke}}
                </p>
                <nuxt-link to="/jokes">back to jockes</nuxt-link>
                </p>
            </div>
        </div>
    </div>
</div>

</div>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            joke: "success",
            baseUrl: 'https://icanhazdadjoke.com',
        }
    },
    async created() {
        const config = {
            headers: {
                'Accept': 'application/json'
            }
        }
        try {
            const res = await axios.get(`${this.baseUrl}/j/${this.$route.params.id}`, config);
            console.log(res.data);
            this.joke = res.data.joke;
        } catch (e) {
            console.log(e.message)
        }
    }
}
</script>

<style>
.videobg {
    position: relative;
    background-color: black;
    height: 100vh;
    min-height: 25rem;
    width: 100%;
    overflow: hidden;
}

.videobg video {
    position: absolute;
    top: 50%;
    left: 50%;
    min-width: 100%;
    min-height: 100%;
    width: auto;
    height: auto;
    z-index: 0;
    -ms-transform: translateX(-50%) translateY(-50%);
    -moz-transform: translateX(-50%) translateY(-50%);
    -webkit-transform: translateX(-50%) translateY(-50%);
    transform: translateX(-50%) translateY(-50%);
}

.videobg .container {
    position: relative;
    z-index: 2;
}

.videobg .overlay {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    background-color: black;
    opacity: 0.5;
    z-index: 1;
}

@media (pointer: coarse) and (hover: none) {
    .videobg {
        background: url('https://source.unsplash.com/XT5OInaElMw/1600x900') black no-repeat center center scroll;
    }

    .videobg video {
        display: none;
    }
}
</style>
