<template>
    <div className="results-table">
        <div className="results-A">
            <div className="results-letter">A</div>
            <div className="results-container">
                <div className="results-list">{ AScores }</div>
            </div>
        </div>
        <div className="results-B">
            <div className="results-letter">B</div>
            <div className="results-container">
                <div className="results-list">{ BScores }</div>
            </div>
        </div>
        <div className="results-C">
            <div className="results-letter">C</div>
            <div className="results-container">
                <div className="results-list">{ CScores }</div>
            </div>
        </div>
        <div className="results-D">
            <div className="results-letter">D</div>
            <div className="results-container">
                <div className="results-list">{ DScores }</div>
            </div>
        </div>
        <div className="results-E">
            <div className="results-letter">E</div>
            <div className="results-container">
                <div className="results-list">{ EScores }</div>
            </div>
        </div>
        <div className="results-F">
            <div className="results-letter">F</div>
            <div className="results-container">
                <div className="results-list">{ FScores }</div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    
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