<template>
  <!-- <h1>This is a Child Component in Vue Js</h1> -->
  <h5 v-for="user in userdata" :key="user.name">
    {{ user.name }}-->{{ user.email }}
  </h5>
   <h1 v-bind:style="{ background: 'lightgreen' }">Send Props From Child To Parent.</h1> 
  <button v-on:click="updateParentTitle">Update Parent Title</button>
</template>
<script>
export default {
  name: "ChildComponent",
  props: ["userdata"],
  methods:{
    updateParentTitle(){
        this.$emit("updateTitleEvent","this is a updated parent title using Child Component");

    }
  }
};
</script>
