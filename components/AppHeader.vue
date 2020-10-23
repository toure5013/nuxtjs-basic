<template lang="fr">
<nav class="navbar navbar-expand-lg navbar-dark bg-warning">
    <div class="container">
        <Nuxt-link class="navbar-brand" to="/">
            <Logo style="height:5vh" />
        </Nuxt-link>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarResponsive" aria-controls="navbarResponsive" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarResponsive">
            <ul class="navbar-nav ml-auto">

                <li class="nav-item active ">
                    <Nuxt-link class="nav-link active" to="/">Home<span class="sr-only">(current)</span></Nuxt-link>
                </li>
                <li class="nav-item ">
                    <Nuxt-link class="nav-link active" to="/about"> About</Nuxt-link>
                </li>
                <li class="nav-item ">
                    <Nuxt-link class="nav-link active" to="/jokes"> Jokes</Nuxt-link>
                </li>
                <li class="nav-item">
                    <Nuxt-link class="nav-link active" to="/contact"> Contact</Nuxt-link>
                </li>
            </ul>
        </div>
    </div>
</nav>
</template>

<script>
export default {
    name: 'AppHeader'
}
</script>

<style>
.navbar {
    height: 7vh;
}

.nav-item {
    color: white;
}
</style>
