<template>
    <div class="results-table">
        <div class="results-A">
            <div class="results-letter">A</div>
            <div class="results-container">
                <div class="results-list">
                    <div 
                        class="company"
                        v-for="result in results.AResults"
                        :key="result.display"
                    >
                    {{ result.display }}
                    </div>
                </div>
            </div>
        </div>
        <div class="results-B">
            <div class="results-letter">B</div>
            <div class="results-container">
                <div class="results-list">
                    <div 
                        class="company"
                        v-for="result in results.BResults"
                        :key="result.display"
                    >
                    {{ result.display }}
                    </div>
                </div>
            </div>
        </div>
        <div class="results-C">
            <div class="results-letter">C</div>
            <div class="results-container">
                <div class="results-list">
                    <div 
                        class="company"
                        v-for="result in results.CResults"
                        :key="result.display"
                    >
                    {{ result.display }}
                    </div>
                </div>
            </div>
        </div>
        <div class="results-D">
            <div class="results-letter">D</div>
            <div class="results-container">
                <div class="results-list">
                    <div 
                        class="company"
                        v-for="result in results.DResults"
                        :key="result.display"
                    >
                    {{ result.display }}
                    </div>
                </div>
            </div>
        </div>
        <div class="results-E">
            <div class="results-letter">E</div>
            <div class="results-container">
                <div class="results-list">
                    <div 
                        class="company"
                        v-for="result in results.EResults"
                        :key="result.display"
                    >
                    {{ result.display }}
                    </div>
                </div>
            </div>
        </div>
        <div class="results-F">
            <div class="results-letter">F</div>
            <div class="results-container">
                <div class="results-list">
                    <div 
                        class="company"
                        v-for="result in results.FResults"
                        :key="result.display"
                    >
                    {{ result.display }}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        results: Object,
    }
}
</script>

<style lang="scss" scoped>

.results-table {
    max-height: 1080px;
    display: flex;
    flex-direction: column;
    width: 800px;
    margin-left: 40px;
    margin-top: 25px;
}

.results-letter {
    width: 120px;
    display: flex;
    text-align: center;
    justify-content: center;
    align-items: center;
    color: $tiWhite;
    font-family: $primaryFont;
    font-size: 72px;
    font-weight: 700;
    margin-top: -5px;
}

.results-list {
    //min-height: 60px;
    //max-height: 300px;
    width: 100%;
    padding: 20px 0;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-auto-rows: 16px;
    grid-gap: 5px;
}

.results-container {
    width: 680px;
    display: flex;
    justify-content: flex-start;
    align-items: center;
}

.results-A, .results-B, .results-C, .results-D, .results-E, .results-F {
    display: flex;

}

.results-A {
    background: $scoreA;
}
.results-B {
    background: $scoreB;
}
.results-C {
    background: $scoreC;
}
.results-D {
    background: $scoreD;
}
.results-E {
    background: $scoreE;
}
.results-F {
    background: $scoreF;
}
</style>