<template>
    <ul>
        <li 
            v-for="choice in bestPracticeChoices" 
            :key="choice.slug"
            :class="activeChoice(choice.slug)"
            :activeSlug="activeSlug"
            @click="setActiveChoice(choice.slug)"
        >
            {{ choice.name }}
        </li>
    </ul>
</template>

<script>
export default {
    props: {
        activeSlug: String,
    },
    data() {
        return {
            bestPracticeChoices: [
                {"name": "Control Environment", "slug": "control"},
                {"name": "Political Contributions", "slug": "political"},
                {"name": "Responsible Lobbying", "slug": "responsible"},
                {"name": "Revolving Door", "slug": "revolving"},
                {"name": "Transparency", "slug": "transparency"},
            ]
        }
    },
    methods: {
        activeChoice(slug) {
            if (slug === this.activeSlug) {
                return "active"
            }
        },
        setActiveChoice(Slug) {
            const newSlug = Slug;
            this.$emit('set-slug', newSlug)
        }
    }
}
</script>

<style lang="scss" scoped>
.active {
    background: $tiPink;
}
</style>