<template>
  <div id="app">
<Formcat></Formcat>

  </div>
</template>

<script>
import Formcat from "./components/Formcat.vue"

export default {
  name: 'App',
  components: {
    Formcat
  }
}
</script>

<style lang="scss">

html{
  background-color: rgb(155, 215, 255);
  margin: 0;
  padding: 0;
  text-align: center;
}

</style>
