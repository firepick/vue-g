<template>

<div id="dev">
    <h3>Row of Columns</h3>
    <g-row>
        <g-col>
            <g-header>City</g-header>
            <g-label>San Francisco</g-label>
            <g-label>Boston</g-label>
            <g-label>Atlanta</g-label>
        </g-col>
        <g-col>
            <g-header>Q3 Sales</g-header>
            <g-number>41.01</g-number>
            <g-number>223.02</g-number>
            <g-number>324.03</g-number>
        </g-col>
        <g-col>
            <g-header>Q4 Sales</g-header>
            <g-number>42.01</g-number>
            <g-number>123.02</g-number>
            <g-number>1,234.03</g-number>
        </g-col>
    </g-row>
    <h3>Rows of Columns of Rows</h3>
    <g-row><g-header>City</g-header>
        <g-row>
            <g-header class="grid-w-2">Quarter</g-header><g-header>Sales</g-header>
        </g-row>
    </g-row>
    <g-row>
        <g-label class="grid-h-2">San Francisco</g-label>
        <g-col>
            <g-row><g-label class="grid-w-2">Q3</g-label><g-number>41.01</g-number></g-row>
            <g-row><g-label class="grid-w-2">Q4</g-label><g-number>42.01</g-number></g-row>
        </g-col>
    </g-row>
    <g-row>
        <g-label class="grid-h-2">Boston</g-label>
        <g-col>
            <g-row><g-label class="grid-w-2">Q3</g-label><g-number>223.02</g-number></g-row>
            <g-row><g-label class="grid-w-2">Q4</g-label><g-number>123.02</g-number></g-row>
        </g-col>
    </g-row>
    <g-row>
        <g-label class="grid-h-2">Atlanta</g-label>
        <g-col>
            <g-row><g-label class="grid-w-2">Q3</g-label><g-number>324.03</g-number></g-row>
            <g-row><g-label class="grid-w-2">Q4</g-label><g-number>1234.03</g-number></g-row>
        </g-col>
    </g-row>
</div>

</template> <!-- ====================================== --> <script>

import Grid from "./grid.vue"

export default {
    name: 'app',
    components: { Grid },
}

</script><!-- ====================================== --> <style>

.grid-cell {
    border-radius: 5px;
    background-color: #eee;
    border: 2pt solid #fff;
}
body {
    padding: 10px;
}

</style>
