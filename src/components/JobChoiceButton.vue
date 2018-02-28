<template>
  <div v-on:click='onClick()' class='button--job' :data-id='value'>{{$t(title)}}</div>
</template>

<script>
export default {
  name: 'JobChoiceButton',
  props: {
    value: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    }
  },

  methods: {
    onClick() {
      this.$emit('jobSelected',{job:this.value})
    }
  }

}
</script>

<style lang="scss" scoped>
  .button--job {
    margin-top: 16px;
    line-height: 56px;
    background: white;
    color: #000;
    width: 100%;
    height: 56px;
    font-weight: 800;
    font-size: 22px;
    letter-spacing: 1.5px;
    border-radius: 8px;
  }
</style>
