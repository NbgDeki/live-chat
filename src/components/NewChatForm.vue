<template>
  <form>
    <textarea
      placeholder="Type a message and hit enter to send..."
      v-model="message"
      @keypress.enter.prevent="handleSubmit"
    ></textarea>
  </form>
</template>

<script>
import { ref } from 'vue';
import getUser from '@/composables/getUser';
import { timestamp } from '@/firebase/config';

export default {
  name: 'NewChatForm',

  setup() {
    const { user } = getUser();
    const message = ref('');

    const handleSubmit = async () => {
      const chat = {
        name: user.value.displayName,
        message: message.value,
        createdAt: timestamp()
      };

      console.log(chat);
      message.value = '';
    };

    return {
      message,
      handleSubmit
    };
  }
};
</script>

<style lang="scss">
form {
  margin: 10px;
}

textarea {
  width: 100%;
  max-width: 100%;
  margin-bottom: 6px;
  padding: 10px;
  box-sizing: border-box;
  border: 0;
  border-radius: 20px;
  font-family: inherit;
  outline: none;
}
</style>
