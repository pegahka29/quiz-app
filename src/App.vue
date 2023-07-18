<template>
    <div id="app">
        <h1>Math Quiz App</h1>
        <button>Addition<br/>+</button>
        <button>Subtraction<br/>-</button>
        <button>Division<br/>/</button>
        <button>Multiplication<br/>*</button>
    </div>
</template>

<script>

export default {
    name: 'App',
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
}

button {
    padding: 10px;
    width: 200px;
    margin-right: 10px;
    height: 80px;
    background-color: #10aeb2;
    color: white;
    font-size: 24px;
    cursor: pointer;
    vertical-align: top;
    border: none;
}
</style>
