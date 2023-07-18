<script>

export default {
    name: "OperatorQuiz",
    props: ['operator']
}
</script>

<template>
    <div>
        <h1>
            {{ operator }}
        </h1>
        <button @click="$emit('onBack')">Back</button>
    </div>
</template>

<style scoped>

</style>
