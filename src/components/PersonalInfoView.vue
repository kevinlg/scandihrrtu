<template>
  <div>
    <h1>{{ $t('personalization_page.we_want_to_know_more') }}</h1>
    <form v-on:submit="onSubmit">
      <input type='text' name='first-name' :placeholder="$t('personalization_page.first_name')" v-model='user.firstName'  required/>
      <input type='text' name='last-name' :placeholder="$t('personalization_page.last_name')"  v-model='user.lastName'  required/>
      <input type='phone' name='phone-number' :placeholder="$t('personalization_page.phone_number')" v-model='user.phone' required/>
      <input type='email' name='email' :placeholder="$t('personalization_page.email')"  v-model='user.email' required />
      <input type='submit' :value="$t('personalization_page.submit')"/>
    </form>
  </div>
</template>

<script>

var user = {
  firstName : '',
  lastName: '',
  phone: '',
  email: ''
};

export default {
  name: 'PersonalInfoView',
  
  data: function(){
    return {
      user: user,
    }
  },

  methods: {
    onSubmit: function(event) {
      this.$emit('userInfosUpdated', {user : this.user})
      this.user.firstName = ''
      this.user.lastName = ''
      this.user.phone= ''
      this.user.email = '' 
      event.preventDefault();
    },
  }
}
</script>


<style lang="scss" scoped>
  $red-scandiweb: #e04f4f;

  input { 
    margin: 24px auto;
    display: block;
    width: 380px;
    height: 48px;
    font-size: 24px;
    padding: 8px;
  }

  input[type='submit'] {
    background: white;
    color: $red-scandiweb;
    border: none;
    border-radius: 8px;
    height: 56px;
    box-shadow: 0px 6px 12px 0px rgba(0, 0, 0, 0.25);
  }
</style>
