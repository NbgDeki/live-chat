<template>
  <div class="welcome container">
    <p>Welcome</p>
    <div v-if="showLogin">
      <h2>Login</h2>
      <LoginForm @login="enterChat"></LoginForm>
      <p>
        No account yet?
        <span @click="showLogin = false">Signup</span> instead
      </p>
    </div>

    <div v-else>
      <h2>Sign up</h2>
      <SignupForm @signup="enterChat"></SignupForm>
      <p>
        Already registered?
        <span @click="showLogin = true">Login</span> instead
      </p>
    </div>
  </div>
</template>

<script>
import SignupForm from '@/components/SignupForm.vue';
import LoginForm from '@/components/LoginForm.vue';
import { ref } from 'vue';
import { useRouter } from 'vue-router';

export default {
  name: 'Welcome',

  components: { SignupForm, LoginForm },

  setup() {
    const showLogin = ref(true);
    const router = useRouter();

    const enterChat = () => {
      router.push({ name: 'chatroom' });
    };

    return {
      showLogin,
      enterChat
    };
  }
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

  span {
    font-weight: bold;
    text-decoration: underline;
    cursor: pointer;
  }

  button {
    margin: 20px auto;
  }
}
</style>
