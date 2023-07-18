<template>
    <div id="app">
        <h1>Math Quiz App</h1>
        <operator-selector
            @changeOperator="changeOperator"
        />
    </div>
</template>

<script>

import OperatorSelector from "@/components/OperatorSelector.vue";

export default {
    name: 'App',
    components: {OperatorSelector},
    data() {
        return {
            operator: null
        }
    },
    methods: {
        changeOperator(operator) {
            this.operator = operator
        }
    },
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
    font-size: 24px;
}

</style>
