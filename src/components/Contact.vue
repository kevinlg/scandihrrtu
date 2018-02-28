

<template>
    <div class='wrapper'>
        <p v-if="positive">{{$t('contact.positive_test')}}</p>
        <p v-else>{{$t('contact.negative_test')}} </p>
        <div v-if='!showDone' class='btn btn--contact-us' @click='getInTouch'>Get in touch</div>
        <p class='done' v-if='showDone'>{{$t('contact.come_speak_with_us')}}</p>
    </div>
</template>

<script>
export default {
    name:'ContactUs',    
    props: ['positive'],
    data(){
      return{
        showDone: false  
      }
    },
    methods: {
        getInTouch() {
          this.showDone = true;
          this.$emit('onContactMe')
        }
    },
    watch: {
        locale (val) {
            console.log('locale ' + val)
            this.$i18n.locale = val
        }
    }
}
</script>

<style lang="scss">

p {
  margin: 16px auto;
  font-size: 18px;
  line-height: 26px;
  max-width: 320px;
}

.done {
  margin: 0 auto;
  font-size: 18px;
  font-weight: 800;
  max-width: 370px;
}

.btn--contact-us {
    margin: 32px auto;
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

.wrapper {
  min-height: 272px;
}

</style>

