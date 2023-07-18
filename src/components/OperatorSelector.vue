<template>
    <div>
        <button @click="$emit('changeOperator','+')">Addition<br/>+</button>
        <button @click="$emit('changeOperator','-')">Subtraction<br/>-</button>
        <button @click="$emit('changeOperator','/')">Division<br/>/</button>
        <button @click="$emit('changeOperator','*')">Multiplication<br/>*</button>
    </div>
</template>

<script>

export default {
    name: "OperatorSelector"
}
</script>


<style scoped>
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
