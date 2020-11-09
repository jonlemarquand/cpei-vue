<template>
    <a className="navCircle" :href="url">{{ name }}</a>
</template>

<script>
export default {
    props: {
        url: String,
        name: String,
    }
}
</script>

<style lang="scss" scoped>
.navCircle {
    border-radius: 50%;
    background: $tiPink;
    width: 100px;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    color: $tiWhite;
    font-family: $primaryFont;
    font-size: 18px;
    font-weight: 500;
    text-transform: uppercase;
    text-decoration: none;
    text-align: center;
    line-height: 18px;

    &:hover {
        background: $tiGreen;
    }
}
</style>