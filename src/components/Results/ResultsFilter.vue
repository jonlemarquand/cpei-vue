<template>
    <div>
        <h3>Filter By Theme</h3>
        <div className="filter-list">
            <div class="theme-options" 
                v-for="theme in themesList" 
                :key="theme.value"
            >            
                <input type="radio" name="themes" :value="theme.value" :id="theme.value" v-model="activeTheme" />
                <label  :for="theme.value">{{ theme.name }}</label>
            </div>
        </div>
        <h3>Filter By Industry</h3>
        <div className="filter-list">
            <div class="industry-options" 
                v-for="industry in industriesList" 
                :key="industry.value"
            >            
                <input type="radio" name="industries" :value="industry.value" :id="industry.value" v-model="activeIndustry" />
                <label  :for="industry.value">{{ industry.name }}</label>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            activeTheme: 'overall',
            activeIndustry: 'all',
            themesList: [
                {name: "Overall", value: "overall"},
                {name: "Control Environment", value: "control"},
                {name: "Political Contributions", value: "political"},
                {name: "Responsible Lobbying", value: "responsible"},
                {name: "Revolving Door", value: "revolving"},
                {name: "Transparency", value: "transparency"}
            ],
            industriesList: [
                {name: "All", value: "all"},
                {name:"Accounting and Consultancy", value:"accounting"},
                {name:"Automotive", value: "automotive"},
                {name:"Banking and Financial Services", value: "banking"},
                {name:"Consumer Products", value:"consumer"},
                {name:"Economic Goods", value: "economic"},
                {name:"Energy and Utilities", value: "energy"},
                {name:"Engineering and Manufacturing", value: "engineering"},
                {name:"Multi-Industry", value: "multi"},
                {name:"Pharmaceutical", value: "pharma"},
                {name:"Technology, Software and Business Services", value: "tech"},
                {name:"Telecommunication and Media", value: "telecomms"}
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
    .filter-list {
        .theme-options, .industry-options {
            color: $tiWhite;
            background: $tiBlue;
            font-family: $primaryFont;
            text-transform: uppercase;
            font-weight: 700;
            //padding: 4px 5px 5px 5px;
            display: flex;
            flex-direction: column;
            width: 100%;

            &:focus-within {
                outline: 3px $tiGreen solid;
            }
        
        input, label {
            padding: 5px;
        }
        
        input:checked + label {
            background: $tiPink;
        }
    
        &:hover, label:hover {
            background: $tiGreen;
            cursor: pointer;
        }

        input {
            opacity: 0;
            width: 0;
            height: 0;
        }
        }
    }
</style>