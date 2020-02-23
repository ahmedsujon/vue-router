<template>
  <div class="profile">
    <h1>Profile User ID {{ userId }}</h1>
  </div>
</template>

<script>
export default {
  name: "Profile",
  data() {
    return {
      userId: this.$route.params.user_id
    };
  },
  methods: {
    updateId() {
      this.userId = this.$route.params.user_id;
    }
  },
  watch: {
    $route: "updateId"
  }
};
</script>

<style scoped>
h1 {
  color: green;
}
</style>
