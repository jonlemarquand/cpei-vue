<template>
    <div id="results">
        <h2>Results</h2>
        <div className="results-section">
        <ResultsFilter 
            @set-theme="setNewTheme"
            @set-industry="setNewIndustry"
        />
        <ResultsTable 
            :results="scoresData()"
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
    },
    data() {
        return {
            activeTheme: 'overall',
            activeIndustry: 'all',
            cpeiData: [
                {
                "display": "3M",
                "overall": "B",
                "control": "A",
                "political": "B",
                "responsible": "C",
                "revolving": "C",
                "transparency": "A",
                "government": true,
                "industry": "multi"
                },
                {
                "display": "AB InBev",
                "overall": "E",
                "control": "D",
                "political": "E",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "consumer"
                },
                {
                "display": "ABB",
                "overall": "E",
                "control": "E",
                "political": "E",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "multi"
                },
                {
                "display": "Amazon",
                "overall": "E",
                "control": "D",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "consumer"
                },
                {
                "display": "Anglo American",
                "overall": "C",
                "control": "B",
                "political": "A",
                "responsible": "D",
                "revolving": "E",
                "transparency": "C",
                "government": null,
                "industry": "economic"
                },
                {
                "display": "Apple Inc",
                "overall": "C",
                "control": "B",
                "political": "A",
                "responsible": "D",
                "revolving": "E",
                "transparency": "C",
                "government": true,
                "industry": "tech"
                },
                {
                "display": "Associated British Foods",
                "overall": "E",
                "control": "E",
                "political": "A",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "consumer"
                },
                {
                "display": "Associated British Ports",
                "overall": "F",
                "control": "F",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "energy"
                },
                {
                "display": "AstraZeneca",
                "overall": "E",
                "control": "C",
                "political": "F",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "pharma"
                },
                {
                "display": "Atkins (part of SNC Lavalin)",
                "overall": "C",
                "control": "B",
                "political": "B",
                "responsible": "C",
                "revolving": "D",
                "transparency": "C",
                "government": true,
                "industry": "engineering"
                },
                {
                "display": "Aviva",
                "overall": "D",
                "control": "B",
                "political": "C",
                "responsible": "E",
                "revolving": "F",
                "transparency": "A",
                "government": true,
                "industry": "banking"
                },
                {
                "display": "Babcock",
                "overall": "E",
                "control": "C",
                "political": "F",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "engineering"
                },
                {
                "display": "BAE Systems",
                "overall": "D",
                "control": "C",
                "political": "B",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "multi"
                },
                {
                "display": "Balfour Beatty",
                "overall": "E",
                "control": "C",
                "political": "F",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "multi"
                },
                {
                "display": "Barclays",
                "overall": "B",
                "control": "A",
                "political": "B",
                "responsible": "B",
                "revolving": "E",
                "transparency": "A",
                "government": true,
                "industry": "banking"
                },
                {
                "display": "BASF",
                "overall": "C",
                "control": "C",
                "political": "B",
                "responsible": "D",
                "revolving": "B",
                "transparency": "A",
                "government": true,
                "industry": "economic"
                },
                {
                "display": "BAT",
                "overall": "C",
                "control": "C",
                "political": "C",
                "responsible": "C",
                "revolving": "E",
                "transparency": "A",
                "government": null,
                "industry": "consumer"
                },
                {
                "display": "BHP",
                "overall": "C",
                "control": "C",
                "political": "A",
                "responsible": "C",
                "revolving": "E",
                "transparency": "A",
                "government": null,
                "industry": "economic"
                },
                {
                "display": "BMW",
                "overall": "E",
                "control": "F",
                "political": "A",
                "responsible": "F",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "automotive"
                },
                {
                "display": "Bombardier",
                "overall": "F",
                "control": "E",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "engineering"
                },
                {
                "display": "BP",
                "overall": "E",
                "control": "E",
                "political": "B",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "energy"
                },
                {
                "display": "BT Group",
                "overall": "D",
                "control": "D",
                "political": "A",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "telecomms"
                },
                {
                "display": "Caterpillar",
                "overall": "E",
                "control": "C",
                "political": "F",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "engineering"
                },
                {
                "display": "Centrica",
                "overall": "B",
                "control": "A",
                "political": "B",
                "responsible": "C",
                "revolving": "E",
                "transparency": "A",
                "government": true,
                "industry": "energy"
                },
                {
                "display": "Cisco",
                "overall": "C",
                "control": "B",
                "political": "C",
                "responsible": "C",
                "revolving": "F",
                "transparency": "A",
                "government": true,
                "industry": "tech"
                },
                {
                "display": "CK Hutchinson",
                "overall": "F",
                "control": "F",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "multi"
                },
                {
                "display": "Coca-Cola",
                "overall": "D",
                "control": "C",
                "political": "F",
                "responsible": "E",
                "revolving": "E",
                "transparency": "C",
                "government": true,
                "industry": "consumer"
                },
                {
                "display": "Compass Group",
                "overall": "E",
                "control": "D",
                "political": "A",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": null,
                "industry": "consumer"
                },
                {
                "display": "CRH",
                "overall": "E",
                "control": "D",
                "political": "E",
                "responsible": "D",
                "revolving": "F",
                "transparency": "F",
                "government": null,
                "industry": "economic"
                },
                {
                "display": "Deloitte",
                "overall": "D",
                "control": "D",
                "political": "A",
                "responsible": "E",
                "revolving": "D",
                "transparency": "C",
                "government": null,
                "industry": "accounting"
                },
                {
                "display": "Diageo",
                "overall": "F",
                "control": "E",
                "political": "E",
                "responsible": "F",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "consumer"
                },
                {
                "display": "Disney",
                "overall": "F",
                "control": "E",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "telecomms"
                },
                {
                "display": "DP World",
                "overall": "E",
                "control": "E",
                "political": "A",
                "responsible": "F",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "energy"
                },
                {
                "display": "E.ON",
                "overall": "E",
                "control": "E",
                "political": "B",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "energy"
                },
                {
                "display": "EISAI",
                "overall": "E",
                "control": "C",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "pharma"
                },
                {
                "display": "Equinor (Formerly Statoil)",
                "overall": "C",
                "control": "B",
                "political": "A",
                "responsible": "C",
                "revolving": "F",
                "transparency": "A",
                "government": true,
                "industry": "energy"
                },
                {
                "display": "Experian",
                "overall": "C",
                "control": "B",
                "political": "C",
                "responsible": "D",
                "revolving": "F",
                "transparency": "A",
                "government": null,
                "industry": "tech"
                },
                {
                "display": "EY",
                "overall": "F",
                "control": "F",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": null,
                "industry": "accounting"
                },
                {
                "display": "Facebook",
                "overall": "E",
                "control": "C",
                "political": "C",
                "responsible": "F",
                "revolving": "D",
                "transparency": "C",
                "government": true,
                "industry": "tech"
                },
                {
                "display": "Ford",
                "overall": "F",
                "control": "F",
                "political": "F",
                "responsible": "F",
                "revolving": "D",
                "transparency": "C",
                "government": true,
                "industry": "automotive"
                },
                {
                "display": "General Electric",
                "overall": "D",
                "control": "C",
                "political": "B",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "multi"
                },
                {
                "display": "GKN",
                "overall": "F",
                "control": "E",
                "political": "B",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "engineering"
                },
                {
                "display": "GlaxoSmithKline",
                "overall": "A",
                "control": "A",
                "political": "B",
                "responsible": "B",
                "revolving": "A",
                "transparency": "A",
                "government": true,
                "industry": "pharma"
                },
                {
                "display": "Glencore",
                "overall": "E",
                "control": "D",
                "political": "C",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": null,
                "industry": "economic"
                },
                {
                "display": "Google",
                "overall": "D",
                "control": "D",
                "political": "C",
                "responsible": "D",
                "revolving": "F",
                "transparency": "A",
                "government": true,
                "industry": "tech"
                },
                {
                "display": "Hitachi",
                "overall": "F",
                "control": "E",
                "political": "E",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "multi"
                },
                {
                "display": "Honda",
                "overall": "F",
                "control": "F",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "automotive"
                },
                {
                "display": "HP Enterprise",
                "overall": "D",
                "control": "C",
                "political": "C",
                "responsible": "E",
                "revolving": "E",
                "transparency": "A",
                "government": true,
                "industry": "tech"
                },
                {
                "display": "HSBC",
                "overall": "D",
                "control": "B",
                "political": "B",
                "responsible": "F",
                "revolving": "E",
                "transparency": "C",
                "government": null,
                "industry": "banking"
                },
                {
                "display": "Huawei",
                "overall": "F",
                "control": "F",
                "political": "C",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "tech"
                },
                {
                "display": "Iberdrola",
                "overall": "C",
                "control": "B",
                "political": "C",
                "responsible": "C",
                "revolving": "F",
                "transparency": "A",
                "government": true,
                "industry": "energy"
                },
                {
                "display": "IBM",
                "overall": "B",
                "control": "A",
                "political": "A",
                "responsible": "C",
                "revolving": "D",
                "transparency": "C",
                "government": true,
                "industry": "tech"
                },
                {
                "display": "Imagination Technologies",
                "overall": "F",
                "control": "F",
                "political": "A",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "tech"
                },
                {
                "display": "Imperial Tobacco",
                "overall": "E",
                "control": "E",
                "political": "A",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": null,
                "industry": "consumer"
                },
                {
                "display": "INEOS",
                "overall": "F",
                "control": "F",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "economic"
                },
                {
                "display": "Jaguar Land Rover",
                "overall": "E",
                "control": "E",
                "political": "B",
                "responsible": "F",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "automotive"
                },
                {
                "display": "JCB",
                "overall": "F",
                "control": "F",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "engineering"
                },
                {
                "display": "Johnson & Johnson",
                "overall": "E",
                "control": "C",
                "political": "F",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "pharma"
                },
                {
                "display": "Johnson Matthey",
                "overall": "E",
                "control": "E",
                "political": "E",
                "responsible": "F",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "economic"
                },
                {
                "display": "KPMG",
                "overall": "C",
                "control": "B",
                "political": "B",
                "responsible": "C",
                "revolving": "F",
                "transparency": "C",
                "government": null,
                "industry": "accounting"
                },
                {
                "display": "Legal & General",
                "overall": "D",
                "control": "B",
                "political": "A",
                "responsible": "F",
                "revolving": "F",
                "transparency": "C",
                "government": null,
                "industry": "banking"
                },
                {
                "display": "Lloyds",
                "overall": "D",
                "control": "A",
                "political": "A",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": null,
                "industry": "banking"
                },
                {
                "display": "Lockheed Martin",
                "overall": "C",
                "control": "A",
                "political": "B",
                "responsible": "E",
                "revolving": "E",
                "transparency": "C",
                "government": true,
                "industry": "multi"
                },
                {
                "display": "Microsoft",
                "overall": "C",
                "control": "B",
                "political": "B",
                "responsible": "C",
                "revolving": "E",
                "transparency": "A",
                "government": true,
                "industry": "tech"
                },
                {
                "display": "Mitsubishi Heavy Industries",
                "overall": "F",
                "control": "E",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "multi"
                },
                {
                "display": "Mondelez International",
                "overall": "F",
                "control": "F",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "consumer"
                },
                {
                "display": "National Grid",
                "overall": "B",
                "control": "A",
                "political": "B",
                "responsible": "B",
                "revolving": "B",
                "transparency": "A",
                "government": true,
                "industry": "energy"
                },
                {
                "display": "Nestlé",
                "overall": "D",
                "control": "D",
                "political": "F",
                "responsible": "C",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "consumer"
                },
                {
                "display": "Nissan",
                "overall": "F",
                "control": "F",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "automotive"
                },
                {
                "display": "Novartis",
                "overall": "E",
                "control": "F",
                "political": "F",
                "responsible": "E",
                "revolving": "D",
                "transparency": "C",
                "government": true,
                "industry": "pharma"
                },
                {
                "display": "P&G",
                "overall": "E",
                "control": "D",
                "political": "E",
                "responsible": "F",
                "revolving": "E",
                "transparency": "C",
                "government": true,
                "industry": "consumer"
                },
                {
                "display": "PCCW",
                "overall": "F",
                "control": "F",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "telecomms"
                },
                {
                "display": "Pearson",
                "overall": "B",
                "control": "A",
                "political": "A",
                "responsible": "B",
                "revolving": "A",
                "transparency": "A",
                "government": true,
                "industry": "telecomms"
                },
                {
                "display": "PepsiCo",
                "overall": "E",
                "control": "C",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "consumer"
                },
                {
                "display": "Pfizer",
                "overall": "E",
                "control": "C",
                "political": "E",
                "responsible": "F",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "pharma"
                },
                {
                "display": "Prudential",
                "overall": "E",
                "control": "E",
                "political": "A",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "banking"
                },
                {
                "display": "PwC",
                "overall": "D",
                "control": "C",
                "political": "A",
                "responsible": "E",
                "revolving": "D",
                "transparency": "C",
                "government": null,
                "industry": "accounting"
                },
                {
                "display": "RB Group",
                "overall": "E",
                "control": "C",
                "political": "C",
                "responsible": "F",
                "revolving": "F",
                "transparency": "C",
                "government": null,
                "industry": "consumer"
                },
                {
                "display": "RBS",
                "overall": "D",
                "control": "C",
                "political": "A",
                "responsible": "E",
                "revolving": "D",
                "transparency": "C",
                "government": null,
                "industry": "banking"
                },
                {
                "display": "RELX",
                "overall": "E",
                "control": "C",
                "political": "F",
                "responsible": "F",
                "revolving": "E",
                "transparency": "C",
                "government": null,
                "industry": "tech"
                },
                {
                "display": "Rio Tinto",
                "overall": "E",
                "control": "D",
                "political": "A",
                "responsible": "E",
                "revolving": "E",
                "transparency": "C",
                "government": null,
                "industry": "economic"
                },
                {
                "display": "Roche",
                "overall": "D",
                "control": "E",
                "political": "E",
                "responsible": "C",
                "revolving": "E",
                "transparency": "C",
                "government": true,
                "industry": "pharma"
                },
                {
                "display": "Rolls-Royce",
                "overall": "E",
                "control": "D",
                "political": "A",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "engineering"
                },
                {
                "display": "RWE",
                "overall": "C",
                "control": "A",
                "political": "A",
                "responsible": "C",
                "revolving": "E",
                "transparency": "C",
                "government": true,
                "industry": "energy"
                },
                {
                "display": "Sabic",
                "overall": "E",
                "control": "E",
                "political": "F",
                "responsible": "F",
                "revolving": "E",
                "transparency": "C",
                "government": true,
                "industry": "economic"
                },
                {
                "display": "SAGE",
                "overall": "F",
                "control": "F",
                "political": "E",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "tech"
                },
                {
                "display": "Samsung",
                "overall": "F",
                "control": "F",
                "political": "A",
                "responsible": "F",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "multi"
                },
                {
                "display": "Shell",
                "overall": "E",
                "control": "D",
                "political": "B",
                "responsible": "E",
                "revolving": "E",
                "transparency": "C",
                "government": true,
                "industry": "energy"
                },
                {
                "display": "Shire",
                "overall": "D",
                "control": "C",
                "political": "E",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": null,
                "industry": "pharma"
                },
                {
                "display": "Siemens",
                "overall": "B",
                "control": "A",
                "political": "B",
                "responsible": "B",
                "revolving": "D",
                "transparency": "A",
                "government": true,
                "industry": "engineering"
                },
                {
                "display": "Sky",
                "overall": "B",
                "control": "A",
                "political": "A",
                "responsible": "C",
                "revolving": "E",
                "transparency": "A",
                "government": null,
                "industry": "telecomms"
                },
                {
                "display": "Softbank",
                "overall": "F",
                "control": "E",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "multi"
                },
                {
                "display": "SSE",
                "overall": "B",
                "control": "A",
                "political": "A",
                "responsible": "C",
                "revolving": "D",
                "transparency": "A",
                "government": true,
                "industry": "energy"
                },
                {
                "display": "Standard Chartered",
                "overall": "B",
                "control": "A",
                "political": "A",
                "responsible": "C",
                "revolving": "F",
                "transparency": "A",
                "government": null,
                "industry": "banking"
                },
                {
                "display": "Syngenta",
                "overall": "E",
                "control": "E",
                "political": "F",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "economic"
                },
                {
                "display": "TATA Group",
                "overall": "F",
                "control": "E",
                "political": "E",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "multi"
                },
                {
                "display": "Telefonica",
                "overall": "C",
                "control": "B",
                "political": "A",
                "responsible": "D",
                "revolving": "D",
                "transparency": "A",
                "government": true,
                "industry": "telecomms"
                },
                {
                "display": "Tesco",
                "overall": "E",
                "control": "E",
                "political": "A",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": null,
                "industry": "consumer"
                },
                {
                "display": "Time Warner",
                "overall": "E",
                "control": "D",
                "political": "C",
                "responsible": "F",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "telecomms"
                },
                {
                "display": "Toshiba",
                "overall": "F",
                "control": "F",
                "political": "F",
                "responsible": "F",
                "revolving": "E",
                "transparency": "F",
                "government": true,
                "industry": "engineering"
                },
                {
                "display": "Toyota",
                "overall": "F",
                "control": "F",
                "political": "F",
                "responsible": "F",
                "revolving": "F",
                "transparency": "F",
                "government": true,
                "industry": "automotive"
                },
                {
                "display": "Unilever",
                "overall": "D",
                "control": "D",
                "political": "A",
                "responsible": "E",
                "revolving": "F",
                "transparency": "C",
                "government": true,
                "industry": "consumer"
                },
                {
                "display": "Vodafone",
                "overall": "C",
                "control": "B",
                "political": "A",
                "responsible": "D",
                "revolving": "B",
                "transparency": "A",
                "government": null,
                "industry": "telecomms"
                },
                {
                "display": "WPP",
                "overall": "C",
                "control": "B",
                "political": "E",
                "responsible": "D",
                "revolving": "C",
                "transparency": "C",
                "government": true,
                "industry": "tech"
                }
            ]

        }
    },
    methods: {
        scoresData() {
            const activeCompanies = this.cpeiData.filter(company => this.activeIndustry === 'all' || company.industry === this.activeIndustry);

            const AScores = activeCompanies.filter(company => company[this.activeTheme] === 'A');
            const BScores = activeCompanies.filter(company => company[this.activeTheme] === 'B');
            const CScores = activeCompanies.filter(company => company[this.activeTheme] === 'C');
            const DScores = activeCompanies.filter(company => company[this.activeTheme] === 'D');
            const EScores = activeCompanies.filter(company => company[this.activeTheme] === 'E');
            const FScores = activeCompanies.filter(company => company[this.activeTheme] === 'F');

            const resultsData = {
                AResults: AScores,
                BResults: BScores,
                CResults: CScores,
                DResults: DScores,
                EResults: EScores,
                FResults: FScores,
            }
            //console.log(AScores);
            return resultsData;
        },
        setNewTheme(Theme) {
            this.activeTheme = Theme
        },
        setNewIndustry(Industry) {
            this.activeIndustry = Industry
        }
    }
}
</script>

<style lang="scss">
.results-section {
    display: flex;
}

.company {
    font-family: $primaryFont;
    font-weight: 500;
    font-size: 15px;
    color: $tiWhite;
}
</style>