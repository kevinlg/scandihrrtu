
<template>
    <div>
        <h1>{{question.title}}</h1>
         <div v-for="(answer, index) in question.possibles" 
         :key="index" 
         @click="answerSelected(index)" 
         class='but--answer'>
             {{answer}}
         </div>
    </div>
</template>

<script>

export default {
  name: 'Question',
  props: ['question'],
  methods : {
      answerSelected(index) {
          this.$emit('answer', {correct : index == this.question.answer });
      }
  },
}
</script>

<style lang="scss" scoped>
  .but--answer {
      display: flex;
      justify-content: center;
      align-items: center;
      background:white;
      color: black;
      font-size: 24px;
      padding: 16px;
      font-weight: 700;
      width: 90%;
      margin: 16px auto 0;
  }
</style>