<template>
  <div >
      <h1>Here are you result</h1>
      <div class='score--big'>{{result.correct}}/{{result.questionTaken}}</div>      
      <div @click='onNext' class='but but--next'>Next</div>
  </div>
</template>

<script>
export default {
  name: 'Result',
  props: ['result'],
  methods: {
      onNext() {
          this.$emit('onResultSeen');
      }
  }
}
</script>



<style lang="scss">
    .score--big {
        margin: 72px;
        color: white;
        font-size: 140px;
        letter-spacing: 14px;
    }

    .but--next {
        margin: 16px auto;
        line-height: 56px;
        background: white;
        color: #000;
        width: 100%;
        height: 56px;
        font-weight: 800;
        font-size: 22px;
        letter-spacing: 1.5px;
        border-radius: 8px;
        max-width: 256px;
  }
</style>
