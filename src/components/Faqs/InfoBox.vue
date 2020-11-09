<template>
    <div className="infobox">
        <div class="infobox-header">
            <h3>{{ headerText }}</h3>
            <div class="crossOpen">&#43;</div>
        </div>
        <slots></slots>
    </div>
</template>

<script>
export default {
    props: {
        headerText: String,
    }
}
</script>

<style lang="scss" scoped>

.infobox {
    margin: 10px 0;
}

.infobox-header {
    padding: 15px;
    background: $tiBlue;
    display: flex;
    justify-content: space-between;
    align-items: center;

    h3 {
        color: $tiWhite;
        margin: 0;
        text-transform: uppercase;
        font-size: 18px;
    }

    .crossOpen {
        display: flex;
        height: 40px;
        justify-content: center;
        align-items: center;
        text-align: center;
        font-size: 48px;
        font-family: $primaryFont;
        font-weight: 500;
        color: $tiWhite;
        margin: 0;
        margin-left: 20px;
        transition: 0.3s ease-out;

        &.active {
            transform: rotate(45deg);
        }
    }

    &.active {
        background: $tiPink;
    }

    &:hover {
        background: $tiGreen;
        cursor: pointer;
    }
}

.infobox-content {
    background: $tiWhite;
    padding: 15px;
    &.decoBox {
        padding: 0;
    }
}

.infobox-display-enter {
    max-height: 0px;
    overflow: hidden;
}

.infobox-display-enter-active {
    max-height: 1200px;
    transition: max-height .3s ease;
}

.infobox-display-exit {
    max-height: 1200px;
}

.infobox-display-exit-active {
    max-height: 0;
    transition: max-height .3s ease;
    overflow: hidden;
}

</style>