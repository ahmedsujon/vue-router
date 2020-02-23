<template>
  <div>
    <nav>
      <ul>
        <li>
          <router-link to="/">Home</router-link>
        </li>
        <li>
          <router-link to="/about">About</router-link>
        </li>
        <li>
          <router-link :to="{name: 'contact'}">Contact</router-link>
        </li>
      </ul>
    </nav>
    <div>
      <ul>
        <li v-for="(id,index) in userIds" :key="index">
          <router-link :to="{name: 'profile', params:{user_id: id}}">Profile {{ id }}</router-link>
        </li>
      </ul>
      <button @click="Contact">Contact</button>
      <button @click="About">About</button>
      <button @click="Back">Back</button>
      <button @click="Next">Next</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      userIds: ["1", "3", "2", "4", "5"]
    };
  },
  methods: {
    Contact() {
      this.$router.push({ name: "contact" });
    },
    About() {
      this.$router.push({ name: "About" });
    },
    Back() {
      this.$router.go(-1);
    },
    Next() {
      this.$router.go(1);
    }
  }
};
</script>

<style scoped>
nav {
  text-align: center;
}
nav ul {
  padding: 0px;
}
nav li {
  display: inline-block;
  list-style-type: none;
  margin: 0px;
  padding: 8px;
}
</style>
