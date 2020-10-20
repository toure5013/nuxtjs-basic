<template lang="fr">
<div>
    {{title}}
</div>
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

</style>
