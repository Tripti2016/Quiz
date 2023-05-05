<template>
    <div class="quiz">
        <div v-if="!finished" class="quiz-box">
            <div class="question">
                <h3>{{ currentQuestion.question }}</h3>
            </div>
            <div class="answers">
                <div v-for="(answer, index) in currentQuestion.answers" :key="index+1" @click="submitAnswer(answer)">
                    <p>{{ answer }}</p>
                </div>
            </div>
            <div class="progress">
                <p>Question {{ currentIndex + 1 }} of {{ questions.length }}</p>
            </div>
        </div>
        <!-- <div v-else>
            <h3>Results:</h3>
            <p>You got {{ correctAnswers }} out of {{ questions.length }} questions correct!</p>
            <ul>
                <li v-for="(question, index) in questions" :key="index">
                    {{ question.question }} - {{ question.correctAnswer }} (Your answer: {{ userAnswers[index] }})
                </li>
            </ul>
        </div> -->
        <div class="result-container" v-else>
            <h3>Your Score: {{ score }} / {{ questions.length }}</h3>
            <button class="restart-button" @click="restartQuiz">Restart Quiz</button>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'Quiz',
    props: {
        questions: {
            type: Array,
            required: true,
        },
    },
    data() {
        return {
            currentIndex: 0,
            currentQuestion: this.questions[0],
            finished: false,
            correctAnswers: 0,
            showQuiz: true,
            score: 0,
            // userAnswers: [],
        };
    },
    methods: {
        submitAnswer(answer) {
            // this.userAnswers.push(answer);
            if (answer === this.currentQuestion.correctAnswer) {
                this.correctAnswers++;
                this.score++;
            }
            if (this.currentIndex === this.questions.length - 1) {
                this.finished = true;
                this.showQuiz = false;
            } else {
                this.currentIndex++;
                this.currentQuestion = this.questions[this.currentIndex];
            }
        },
        restartQuiz() {
            this.currentIndex = 0;
            this.currentQuestion = this.questions[0];
            this.showQuiz = true;
            this.score = 0;
            this.finished = false;
        },
    },
};
</script>
