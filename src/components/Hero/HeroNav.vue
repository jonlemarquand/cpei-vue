<template>
    <div className="heroNav">
        <NavCircle name="Results" url="#results" />
        <NavCircle name="Best Practice" url="#best-practice" />
        <NavCircle name="Test Yourself" url="#test" />
        <NavCircle name="FAQs" url="#faqs" />
        <NavCircle name="Resources" url="#resources" />
    </div>
</template>

<script>

import NavCircle from './NavCircle';

export default {
    components: {
        NavCircle
    }
}
</script>

<style lang="scss" scoped>
.heroNav {
    display: flex;
    justify-content: space-evenly;
    margin: 20px auto;
    width: 800px;
}
</style>