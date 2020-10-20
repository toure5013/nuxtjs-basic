<template lang="fr">
<div class="row">
    <Nuxt-link :to="'/jokes/' + id" class="row">
        <div class="col-2 col-xs-4">
            <p v-if="1" class="{ index%2 == 0, alert alert-success : alert alert-info }">{{id}}</p>
        </div>
        <div class=" col-10 col-xs-8">
            <p v-if="1" class="{ index/2 == 0, alert alert-success : alert alert-success }">{{joke}}</p>
        </div>
    </Nuxt-link>
</div>
</template>

<script>
export default {
    name: 'Joke',
    props: ['joke', 'id', 'index'],
    data() {
        return {
            alert: "success"
        }
    },

}
</script>

<style>
* {
    margin: 0;
    padding: 0;
}
</style>
