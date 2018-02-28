<template>
  <div>
    <div> {{currentQuestion + 1 }} / {{quiz.questions.length}}</div>
    <div> Score : {{correctAnswer}} / {{questionTaken}}</div>
    <Question 
      :question='quiz.questions[currentQuestion]' 
      @answer='onAnswer'>
    </Question>
  </div>
</template>

<script>
  import Question from '../components/Question.vue'

const quizz = {
  questions: [
      {
        title: 'What is the best programming language ?',
        possibles : [
          'It depends',
          'Python',
          'C++',
          'Java',
        ],
        answer: 0,
      },
      {
        title: 'Wich image compression format does not support transparency ?',
        possibles : [
          'JPEG',
          'PNG',
          'SVG',
          'WebP',
        ],
        answer: 0,
      },
      {
         title: 'Who is known as the inventor of the internet ?',
        possibles : [
          'Bjarne Stroustrup',
          'Larry Page',
          'Linus Torvalds',
          'Tim Berners-Lee'
        ],
        answer: 3,
      }, 
      {
        title: 'What problem is Djisktra algorithm solving ?',
        possibles : [
          'Proportional Integral Derivative',
          'Data hashing',
          'Shortest path calculation',
          'Data sorting',
        ],
        answer: 2,
      },
    ]
  }

  var quizzInProgress = {
    quiz: quizz,
    currentQuestion: 0,
    questionTaken: 0,
    correctAnswer: 0,
  };

  export default {
    name: 'QuizView',
    data : function () {
      return quizzInProgress;
    },
    components: {
      Question
    },
    methods: {
      onAnswer(evt) {
        this.questionTaken ++;
        if (evt.correct) this.correctAnswer ++;
        if (this.questionTaken < this.quiz.questions.length) {
           this.currentQuestion ++;
        } else {
          let questionsTaken = this.questionTaken;
          let correctAnswer = this.correctAnswer;
          this.correctAnswer = 0;
          this.currentQuestion = 0;
          this.questionTaken = 0;
          this.$emit ('quizdone', {
            taken: questionsTaken,
            score: correctAnswer
          });
          
        }
      }
    }
  }
</script>

<style lang="scss">

</style>

