<template>
  <div>

    <h2> {{ pseudo }} !</h2>
    <h2> {{ password }} !</h2>

  </div>

</template>

<script>
import { mapState } from 'vuex';

export default {
  name: 'Master',

  computed: {
    ...mapState(["pseudo"]),
    ...mapState(["password"])
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
