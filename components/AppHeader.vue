<template lang="fr">
<nav class="navbar navbar-expand-sm  navbar-dark bg-warning">
    <a class="navbar-brand" href="#">
        <Logo style="height:5vh" />
    </a>
    <button class="navbar-toggler d-lg-none" type="button" data-toggle="collapse" data-target="#collapsibleNavId" aria-controls="collapsibleNavId" aria-expanded="false" aria-label="Toggle navigation"></button>
    <div class="collapse navbar-collapse float-right" id="collapsibleNavId">
        <ul class="navbar-nav mr-auto mt-2 mt-lg-0">
            <li class="nav-item active ">
                <Nuxt-link class="nav-link active" to="/">Home<span class="sr-only">(current)</span></Nuxt-link>
            </li>
            <li class="nav-item ">
                <Nuxt-link class="nav-link active" to="/about"> About</Nuxt-link>
            </li>
            <li class="nav-item ">
                <Nuxt-link class="nav-link active" to="/jokes"> Jokes</Nuxt-link>
            </li>
        </ul>
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
