<template lang="fr">
<v-parallax class="cont" dark src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg">
    <v-row align="center" justify="center">
        <v-col class="text-center" cols="12">
            <h1 class="display-1 font-weight-thin mb-4">
                Vuetify
            </h1>
            <h4 class="subheading">
                Build your application today!
            </h4>
        </v-col>
    </v-row>
</v-parallax>
</template>

<script>
export default {
    data() {
        return {
            title: "About"
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

}
</script>

<style>
.cont {
    height: 100vh;
}
</style>
