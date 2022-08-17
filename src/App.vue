<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js App" />
  <HomeComponent info="this is a testing home Component" />

  <h1 v-if="show">This is Conditional Rendering</h1>
  <button v-on:click="display">OnClick in Vue js with Condition</button>
  <h3>For Loop in Vue Js</h3>
  <table border="1" width="100%" height="100%" cellspacing="0" cellpadding="0">
    <tr id="Header">
      <!-- Class Binding with id -->
      <td v-bind:style="{ color: 'red' }">
        Name
        <!-- (class binding with style like as inLine Css) -->
      </td>
      <td>Address</td>
      <td>Email</td>
      <td>Mobile No:</td>
      <input type="checkbox" id="checkbox" v-model="checked" />
      <label for="checkbox">{{ checked }}</label>
    </tr>
    <tr v-for="user in usersData" :key="user.email">
      <td>{{ user.name }}</td>
      <td>{{ user.address }}</td>
      <td>{{ user.email }}</td>
      <td>{{ user.mobileNo }}</td>
    </tr>
  </table>
  <h4 v-bind:class="{ display: visibility }" v-on:click="showStyle">
    Class binding with Object
  </h4>
  <h5 v-bind:class="[arrdata]">Class Binding with Array</h5>
  <h1>{{ bindvalue }}</h1>
  <input type="text" v-model="bindvalue" />
  <h1 v-bind:style="{ background: 'lightblue' }">
    Send Props In Child using Array with data method..
  </h1>
  <ChildComponent v-bind:userdata="users" />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import ChildComponent from "./components/Child.vue";
import HomeComponent from "./components/Home.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    HomeComponent,
    ChildComponent,
  },
  methods: {
    display() {
      this.show = !this.show;
    },
    showStyle() {
      this.visibility = !this.visibility;
    },
  },
  data() {
    return {
      show: false,
      usersData: [
        {
          name: "alok",
          address: "indore",
          email: "alok@indore.com",
          mobileNo: 44558636225,
        },
        {
          name: "arjun",
          address: "bhopal",
          email: "arjun@bhopal.com",
          mobileNo: 1234556444,
        },
        {
          name: "prince",
          address: "dewas",
          email: "prince@dewas.com",
          mobileNo: 88789894445,
        },
      ],
      checked: false,
      visibility: false,
      arrdata: "arrdataclass",
      bindvalue: "One-Way Data Binding",
      users: [
        {
          name: "Ankit",
          email: "ankit@ankit.com",
        },
        {
          name: "Arjun",
          email: "arjun@arjun.com",
        },
        {
          name: "Sonam",
          email: "sonam@sonam.com",
        },
        {
          name: "Priya",
          email: "priya@priya.com",
        },
      ],
    };
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  color: #2c3e50;
  margin-top: 60px;
}

#Header {
  background-color: cornflowerblue;
  color: white;
  font-weight: 600;
  height: 40px;
}

table {
  background-color: lightgray;
  text-align: center;
}
.display {
  background-color: bisque;
  color: brown;
  opacity: 2;
  font-size: 40px;
}
.arrdataclass {
  background-color: chocolate;
  color: aliceblue;
  opacity: 1;
  font-size: 20px;
}
</style>
