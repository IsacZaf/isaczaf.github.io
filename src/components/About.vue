<template>
    <div class="about">
        <h1>About me</h1>
    </div>
</template>

<script>
export default {
    name: "About",
};
</script>

<style scoped>
.about {
    background-image: url('~@/assets/millenium.webp');
    background-size: cover;
    background-position: center;
    min-height: 100vh;
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
    background-size: contain;
    background-position: center center;
    overflow-x: hidden;
}
</style>
