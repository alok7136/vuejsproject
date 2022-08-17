<template>
  <!-- <h1>This is a Child Component in Vue Js</h1> -->
  <h5 v-for="user in userdata" :key="user.name">
    {{ user.name }}--{{ user.email }}
  </h5>
</template>
<script>
export default {
  name: "ChildComponent",
  props: ["userdata"],
};
</script>
