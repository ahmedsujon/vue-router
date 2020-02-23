<template>
  <div class="profile">
    <h1>Profile User ID {{ UserId }}</h1>
  </div>
</template>

<script>
export default {
  name: "profile",
  data() {
    return {
      UserId: this.$route.params.user_id
    };
  }
};
</script>

<style>
h1 {
  color: green;
}
</style>
