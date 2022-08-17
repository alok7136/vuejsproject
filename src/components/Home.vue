<template>
  <h1>Hello This is a Home Component</h1>
  <h2>{{ info }}</h2>
</template>
<script>
export default {
  name: "HomeComponent",
  props: {
    info: String,
  },
};
</script>
