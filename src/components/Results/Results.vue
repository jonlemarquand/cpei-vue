<template>
    <div id="results">
        <h2>Results</h2>
        <div className="results-section">
        <ResultsFilter
            theme={theme}
            onThemeChange={onThemeChange}
            industry={industry}
            onIndustryChange={onIndustryChange}
        />
        <ResultsTable 
            AScores={AScores}
            BScores={BScores} 
            CScores={CScores} 
            DScores={DScores} 
            EScores={EScores} 
            FScores={FScores} 
        />
        </div>
    </div>
</template>

<script>

import ResultsFilter from './ResultsFilter';
import ResultsTable from './ResultsTable';

export default {
    components: {
        ResultsFilter,
        ResultsTable
    }
}
</script>

<style lang="scss">
.results-section {
    display: flex;
}

.company {
    font-family: $primaryFont;
    font-weight: 600;
    font-size: 15px;
    color: $tiWhite;
}
</style>