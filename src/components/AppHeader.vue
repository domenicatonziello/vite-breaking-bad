<script>
export default {
    name: 'AppHeader'
}
</script>

<template>
    <header class="container my-3 d-flex justify-content-between align-items-center">
        <h1 class='fw-bold text-warning'> Pokévue </h1>
        <img class="img-fluid" src="https://assets.stickpng.com/images/612ce4761b9679000402af1c.png" alt="pokemon-logo">
    </header>
</template>

<style scoped lang="scss">
header {
    img {
        width: 20%;
    }
}
</style>