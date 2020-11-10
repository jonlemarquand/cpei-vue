<template>
    <div class="publication">
        <img :src="require(`../../assets/publications/${imageSrc}`)" alt="publication" class="pub-img" />
        <a class="pub-btn" :href="`${publicPath}${urlLink}`">Download PDF</a>
    </div>
</template>

<script>
export default {
    props: {
        imageSrc: String,
        urlLink: String,
    },
    data() {
        return {
            publicPath: process.env.BASE_URL
        }
    }
}
</script>

<style lang="scss" scoped>
.publication {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.pub-img {
    width: 275px;
    height: 390px;
}
</style>