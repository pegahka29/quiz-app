<script>

export default {
    name: "OperatorQuiz",
    props: ['operator'],
    data() {
        return {
            operandLeft: null,
            operandRight: null,
            isQuizStarted: false,
            answers:[]
        }
    },
    methods: {
        starQuiz() {
            this.isQuizStarted = true
            this.operandLeft = parseInt(Math.random() * 13)
            this.operandRight = parseInt(Math.random() * 13)
        }
    },
}
</script>

<template>
    <div>
        <div v-if="isQuizStarted">
            <h4>{{ operandLeft }} {{ operator }} {{ operandRight }}</h4>
        </div>
        <div class="quiz">
            <div v-if="!isQuizStarted">
                <button @click="starQuiz">Start</button>
            </div>
            <button @click="$emit('onBack')">Back</button>
        </div>
    </div>
</template>

<style scoped>
.quiz {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
}
</style>
