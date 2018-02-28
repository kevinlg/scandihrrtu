
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
      background:white;
      color: black;
      font-size: 24px;
      font-weight: 700;
      line-height: 56px;
      width: 100%;
      height: 56px;
      margin-top: 16px;
  }
</style>