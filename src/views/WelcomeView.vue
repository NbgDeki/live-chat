<template>
  <div class="welcome container">
    <p>Welcome</p>
    <!-- <SignupForm></SignupForm> -->
    <login-form></login-form>
  </div>
</template>

<script>
import SignupForm from '@/components/SignupForm.vue';
import LoginForm from '@/components/LoginForm.vue';

export default {
  name: 'Welcome',
  components: { SignupForm, LoginForm }
};
</script>

<style lang="scss">
.welcome {
  text-align: center;
  padding: 20px 0;

  form {
    width: 300px;
    margin: 20px auto;
  }

  label {
    display: block;
    margin: 20px 0 10px;
  }

  input {
    width: 100%;
    padding: 10px;
    border-radius: 20px;
    border: 1px solid #eee;
    outline: none;
    columns: #999;
    margin: 10px auto;
  }
}
</style>
