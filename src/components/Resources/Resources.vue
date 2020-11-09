<template>
    <div id="resources">
        <h2>Resources</h2>
        <div className="resources-section">
            <Publication 
                imageSrc="1018_CPEI_Report_Cover-p-500.png"
                urlLink="1018_CPEI_Report_WEB.pdf"
            />
            <Publication 
                imageSrc="wisecounsel2-p-500.jpeg"
                urlLink="TI-UK-WISE-COUNSEL-OR-DARK-ARTS-2015-1.pdf"
            />
            <Publication 
                imageSrc="CPEI_Checklist.jpg" 
                urlLink="CPEI_Checklist_WEB.pdf"
            />
        </div>
        <div className="resources-section">
        <div className="resource-column">
            <h3>Other</h3>
            <a className="pub-btn" href="https://openaccess.transparency.org.uk">Open Access</a>
            <a className="pub-btn" href="https://openaccess.transparency.org.uk">Press Release</a>
        </div>
        <div className="resource-column">
            <h3>Contact</h3>
            <a className="pub-btn" href="mailto:bip@transparency.org.uk">Get in touch</a>
        </div>
        <div className="resource-column">
            <h3>With Thanks</h3>
            <img class="fpf-logo" src="../../assets/fpf-logo.png" alt="Friends Provident Foundation Logo"/>
        </div>
        </div>
    </div>
</template>

<script>

import Publication from './Publication'

export default {
    components: {
        Publication
    }
}
</script>

<style lang="scss">
.resources-section {
    display: flex;
    justify-content: space-between;
}

.resource-column {
    width: 275px;
}

#resources {
    margin-top: 100px;
}

.fpf-logo {
    width: 140px;
}


.pub-btn {
    background: $tiPink;
    color: $tiWhite;
    display: flex;
    align-items: center;
    text-align: center;
    justify-content: center;
    height: 20px;
    width: 120px;
    padding: 9px 15px;
    font-family: $primaryFont;
    font-size: 18px;
    text-decoration: none;
    margin: 20px 0;

    &:hover {
        background: $tiGreen;
    }
}
</style>