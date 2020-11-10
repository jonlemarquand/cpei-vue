<template>
    <div class="bp-content">
        <div class="bp-column-text">
            <h3>{{ title }}</h3>
            <div class="bp-text">
            <slot></slot>
            </div>
            <a :href="`${publicPath}CPEI_QuickGuides_${pdfURL}.pdf`" class="bp-read-more">Read More</a>
            </div>
            <div class="bp-column-img">
                <img :src="require(`../../assets/${imgLink}`)" class="bp-image" alt="40 percent of businesses ranked a to c"/>
            </div>
        </div>
</template>

<script>
export default {
    props: {
        title: String,
        imgLink: String,
        pdfURL: String,
    },
    data() {
        return {
            publicPath: process.env.BASE_URL
        }
    }
}
</script>

<style lang="scss" scoped>
 .bp-read-more {
     font-family: $primaryFont;
     text-decoration: none;
}

.bp-text {
    margin-bottom: 10px;
}

.bp-image {
    width: 100%;
}
</style>