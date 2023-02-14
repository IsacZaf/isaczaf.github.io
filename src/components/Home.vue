<template>
    <div class="home">
        <h1 class="big-text">Home Page</h1>
        <div class="plain-text">
            Home sweet home. Please click on "Cards" to view the good stuff.
            Also, please release new support :)
        </div>
    </div>
</template>

<script>
export default {
    name: "Home",
};
</script>

<style scoped>
.home {
    background-image: url('~@/assets/millenium.webp');
    background-size: cover;
    background-position: center;
    min-height: calc(100vh - 2rem);
    /* Adjust this value to fit the content */
}

body,
html {
    width: 100%;
    height: 100%;
    margin: 0;
    padding: 0;
}

body {
    background-image: url('/assets/millenium.webp');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center center;
}
</style>
