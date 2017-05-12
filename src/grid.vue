<script>

import Vue from 'vue';

var colWidth = 3; // em

var gridCell = function(cols) { return function() { return {
    width: (Number(cols) * colWidth) + "em",
}}};

var methods = {
    emitClick: function() {
        this.$emit("click");
    }
};

var components = {
    grid: Vue.component("grid", { 
        template: '<div class="grid" ><slot></slot></div>',
    }),
    "g-number": Vue.component("g-number", {
        template: '<div class="grid-cell grid-number" @click="emitClick()" ><slot></slot></div>',
        methods,
    }),
    "g-text": Vue.component("g-text", {
        template: '<div class="grid-cell grid-text" @click="emitClick()" ><slot></slot></div>',
        methods,
    }),
    "g-icon": Vue.component("g-icon", {
        template: '<div class="grid-cell grid-icon" @click="emitClick()" ><slot></slot></div>',
        methods,
    }),
    "g-label": Vue.component("g-label", {
        template: '<div class="grid-cell grid-label" @click="emitClick()" ><slot></slot></div>',
        methods,
    }),
    "g-header": Vue.component("g-header", {
        template: '<div class="grid-cell grid-label grid-header" @click="emitClick()" ><slot></slot></div>',
        methods,
    }),
};
components["g-col"] = Vue.component("g-col", { 
    template: '<div class="grid-column" @click="emitClick()" ><slot></slot></div>',
    methods,
});
components["g-row"] = Vue.component("g-row", { 
    template: '<div class="grid-row" @click="emitClick()" ><slot></slot></div>',
    methods,
});

export default {
    components,
};

</script><style>

.grid-column {
    display:flex; 
    flex-direction:column;
    text-align: center;
}
.grid-row {
    text-align: left;
    display:flex; 
    flex-direction:row;
    flex-wrap: wrap;
    align-items: baseline;
}
.grid {
    padding: 0.1em;
}
.grid-cell {
    vertical-align: top;
    padding: 0.0em;
    padding-left: 0.15em;
    padding-right: 0.15em;
}
.grid-row > .grid-cell:first-child {
    padding-left: 0.3em;
}

.grid-text {
    min-width: 27em;
    height: 1.8em;
}
.grid-icon {
    width: 3em;
    text-align: center;
    height: 1.8em;
}
.grid-number {
    width: 9em;
    text-align: right;
    padding-right: 1em;
    height: 1.8em;
}
.grid-label {
    width: 9em;
    height: 1.8em;
}
.grid-header {
    font-weight: 700;
}

.grid-cell.grid-w-1 { width: 3em; }
.grid-cell.grid-w-2 { width: 6em; }
.grid-cell.grid-w-3 { width: 9em; }
.grid-cell.grid-w-4 { width: 12em; }
.grid-cell.grid-w-5 { width: 15em; }
.grid-cell.grid-w-6 { width: 18em; }
.grid-cell.grid-w-7 { width: 21em; }
.grid-cell.grid-w-8 { width: 24em; }
.grid-cell.grid-w-9 { width: 27em; }
.grid-cell.grid-w-10 { width: 30em; }
.grid-cell.grid-w-11 { width: 33em; }
.grid-cell.grid-w-12 { width: 36em; }
.grid-cell.grid-h-1 { height: 1.8em; }
.grid-cell.grid-h-2 { height: 3.6em; }
.grid-cell.grid-h-3 { height: 5.4em; }
.grid-cell.grid-h-4 { height: 7.2em; }
.grid-cell.grid-h-5 { height: 9.0em; }

[clickable]:hover{
    border-radius: 5px;
    border: 1px solid #d0d0d0;
    cursor: pointer;
}

</style>
