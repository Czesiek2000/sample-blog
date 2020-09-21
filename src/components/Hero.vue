<template>
    <div class="hero-image">
        <div class="container">
            <h1><span>sample blog</span></h1>
            <span class="des">sample blog with dummy posts</span>
        </div>
    </div>
</template>

<script>

export default {
    
}

</script>

<style scoped>
.hero-image {
    position: relative;
    height: 500px;
    overflow: hidden;
    background: url('../assets/hero.jpg') no-repeat center;
}

.container {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    overflow: hidden;
    text-align: center;
    font-weight: 700;
    text-transform: uppercase;
    color: white;
}

.container h1 {
    font-size: 72px;
    letter-spacing: 0.2em;
}

.container h1 span {
    padding: 6px 14px;
    display: inline-block;
}

.des {
    margin: 20px;
    display: block;
    font-size: 26px;
    text-shadow: 0 0 10px black;
}

</style>