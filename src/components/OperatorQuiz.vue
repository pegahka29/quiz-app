<script>

export default {
    name: "OperatorQuiz",
    props: ['operator'],
    data() {
        return {
            operandLeft: null,
            operandRight: null,
            isQuizStarted: false,
            answers: [],
            expectedAnswer: null
        }
    },
    methods: {
        starQuiz() {
            this.isQuizStarted = true
            this.operandLeft = parseInt(Math.random() * 13)
            this.operandRight = parseInt(Math.random() * 13)
            const methods = {
                '+': (a, b) => a + b,
                '-': (a, b) => a - b,
                '*': (a, b) => a * b,
                '/': (a, b) => a / b,
            }
            const methodToUse = methods[this.operator]
            this.answers = []
            this.answers.push(methodToUse(this.operandLeft, this.operandRight + 1))
            this.answers.push(methodToUse(this.operandLeft + 1, this.operandRight))
            this.answers.push(methodToUse(this.operandLeft + 1, this.operandRight + 1))
            this.answers.push(methodToUse(this.operandLeft - 1, this.operandRight + 1))
            this.answers.push(methodToUse(this.operandLeft -1, this.operandRight - 1))
            const expectedAnswer = methodToUse(this.operandLeft +1, this.operandRight -1)
            this.answers[parseInt(Math.random() * this.answers.length)] = expectedAnswer
            this.expectedAnswer = expectedAnswer
        },
        selectedAnswer(answerSelected) {
            if (answerSelected !== this.expectedAnswer) {
                alert('Wrong Answer!')
            }
            this.starQuiz()
        }
    },
}
</script>

<template>
    <div>
        <div v-if="isQuizStarted">
            <h4>{{ operandLeft }} {{ operator }} {{ operandRight }}</h4>
            <button @click="selectedAnswer(i)" v-for="(i, index) of answers" :key="index">{{ i }}</button>
        </div>
        <div class="quiz">
            <div v-if="!isQuizStarted">
                <button @click="starQuiz">Start</button>
            </div>
            <button @click="$emit('onBack')" :class="isQuizStarted ? 'back': ''">Back</button>
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

.back {
    margin-top: 10px;
}
</style>
