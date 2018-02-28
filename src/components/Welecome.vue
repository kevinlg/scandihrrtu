<template>
  <div class='main-container'>
    <div class='title'>{{ $t("welecome_page.intro") }} </div>
    <JobChoiceButton @jobSelected='jobSelected' value='intern' title='welecome_page.title_intern'/>
    <JobChoiceButton @jobSelected='jobSelected' value='junior-dev' title='welecome_page.title_junior'/>
    <JobChoiceButton @jobSelected='jobSelected' value='exp-dev' title='welecome_page.title_exp_dev'/>
    <JobChoiceButton @jobSelected='jobSelected' value='pm' title='welecome_page.ttile_pm'/>
    <JobChoiceButton @jobSelected='jobSelected' value='designer' title='welecome_page.title_designer'/>
    <JobChoiceButton @jobSelected='jobSelected' value='marketing' title='welecome_page.title_digital_marketing_specialist'/>
    <JobChoiceButton @jobSelected='jobSelected' value='qa' title='welecome_page.title_qa'/>
    <JobChoiceButton @jobSelected='jobSelected' value='devops' title='welecome_page.title_devops'/>
    <JobChoiceButton @jobSelected='jobSelected' value='admin' title='welecome_page.title_administrative'/>
  </div>
</template>

<script>

import JobChoiceButton from './JobChoiceButton';

export default {
  name: 'WelcomeView',
  components: {
    JobChoiceButton
  },
  // Defint other method o
  methods: {
    jobSelected: function(job){
      this.$emit('jobSelected', {job:job});
    },
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style  lang="scss" scoped>

#logo svg{
  width: 30%;
  fill: #fff;
}

.title {
  margin: 48px auto;
  font-size: 26px;
}
</style>
