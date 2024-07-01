<template>
  <div class="container">
    <navbar></navbar>
    <new-chat-form></new-chat-form>
  </div>
</template>

<script>
import Navbar from '@/components/Navbar.vue';
import getUser from '@/composables/getUser';
import { watch } from 'vue';
import { useRouter } from 'vue-router';
import NewChatForm from '@/components/NewChatForm.vue';

export default {
  name: 'Chatroom',

  components: { Navbar, NewChatForm },

  setup() {
    const { user } = getUser();
    const router = useRouter();

    watch(user, () => {
      if (!user.value) {
        router.push({ name: 'welcome' });
      }
    });
  }
};
</script>

<style lang="scss"></style>
