<template>
<div>
    <form @submit.prevent="onSubmit" class="row">
        <div class="col-6">
            <input type="text" v-model="text" class="form-control" placeholder="Enter your joke name">
        </div>
        <div class="col-6">
            <input type="submit" class="btn btn-success" value="Search jokes">
        </div>
    </form>
</div>
</template>

<script>
export default {
    name: "SearchJoke",
    data() {
        return {
            text: ""
        }
    },
    methods: {
        onSubmit() {
            this.$emit('search-text', this.text)
            this.text = ""
        }
    }
}
</script>

<style>

</style>
