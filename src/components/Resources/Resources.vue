<template>
    <div id="resources">
        <h2>Resources</h2>
        <div className="resources-section">
            <Publication imageSrc="1018_CPEI_Report_Cover-p-500.png"/>
            <Publication imageSrc="wisecounsel2-p-500.jpeg"/>
            <Publication imageSrc="CPEI_Checklist.jpg"/>
        </div>
        <div className="resources-section">
        <div className="resource-column">
            <h3>Other</h3>
            <a className="pub-btn" href="https://openaccess.transparency.org.uk">Open Access</a>
            <a className="pub-btn" href="https://openaccess.transparency.org.uk">Press Release</a>
        </div>
        <div className="resource-column">
            <h3>Contact</h3>
        </div>
        <div className="resource-column">
            <h3>With Thanks</h3>
        </div>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style lang="scss" scoped>
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
</style>