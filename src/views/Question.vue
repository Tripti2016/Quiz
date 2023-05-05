<template lang="">
    <div>
        <Quiz :questions="quizQuestions" @finished="showResults"  />
    </div>
</template>
<script>
import Quiz from '../components/Quiz.vue';
export default {

    components: {
        Quiz
    },
    data() {
        return {
            quizQuestions: [
                {
                    question: 'What is the capital of France?',
                    answers: ['Paris', 'London', 'Berlin', 'Madrid'],
                    correctAnswer: 'Paris',
                },
                {
                    question: 'What is the largest country in the world by land area?',
                    answers: ['Russia', 'Canada', 'China', 'USA'],
                    correctAnswer: 'Russia',
                },
                {
                    question: 'What is the smallest country in the world?',
                    answers: ['Monaco', 'Vatican City', 'San Marino', 'Liechtenstein'],
                    correctAnswer: 'Vatican City',
                }, {
                    question: 'What is the highest mountain in the world?',
                    answers: ['Mount Kilimanjaro', 'Mount Everest', 'Mount Fuji', 'Mount McKinley'],
                    correctAnswer: 'Mount Everest',
                },
                {
                    question: 'What is the largest ocean in the world?',
                    answers: ['Atlantic Ocean', 'Arctic Ocean', 'Indian Ocean', 'Pacific Ocean'],
                    correctAnswer: 'Pacific Ocean',
                },
                {
                    question: 'What is the highest waterfall in the world?',
                    answers: ['Angel Falls', 'Niagara Falls', 'Victoria Falls', 'Iguaçu Falls'],
                    correctAnswer: 'Angel Falls',
                },
                {
                    question: 'What is the capital of India?',
                    answers: ['New Delhi', 'Mumbai', 'Kolkata', 'Chennai'],
                    correctAnswer: 'New Delhi'
                },
                {
                    question: 'What is the national animal of Australia?',
                    answers: ['Kangaroo', 'Koala', 'Emu', 'Tasmanian Devil'],
                    correctAnswer: 'Kangaroo',
                },
                {
                    question: 'What is the largest desert in the world?',
                    answers: ['Sahara', 'Gobi', 'Arabian', 'Mojave'],
                    correctAnswer: 'Sahara',
                },
                {
                    question: 'What is the largest city in the world?',
                    answers: ['Tokyo', 'Mumbai', 'London', 'New-York'],
                    correctAnswer: 'Tokyo',
                },
                
            ],
            showQuizResult: true,
        };
    },
    methods: {
    showResult() {
      this.showQuizResult = true;
    },
  },
}
</script>
