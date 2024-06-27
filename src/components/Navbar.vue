<template>
  <nav>
    <div>
      <p>Hey there... display name here</p>
      <p class="email">Currently logged in as...email</p>
    </div>

    <button>Logout</button>
  </nav>
</template>

<script>
export default {
  name: 'Navbar'
};
</script>

<style lang="scss">
nav {
  padding: 20px;
  border-bottom: 1px solid #eee;
  display: flex;
  justify-content: space-between;
  align-items: center;

  p {
    margin: 2px auto;
    font-size: 16px;
    color: #444;

    &.email {
      font-size: 14px;
      color: #999;
    }
  }
}
</style>
