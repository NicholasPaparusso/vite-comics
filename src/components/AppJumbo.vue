  <script>
  export default {
  name: 'AppJumbo'
  }
  </script>

<template>
  <div class="jumbo">
    <div class="btn">
      <h2>current series</h2>
    </div>
  </div>
</template>


<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixin' as *;
  .jumbo{
    height: 400px;
    background-image: url('../assets/img/jumbotron.jpg');
    background-repeat: no-repeat ;
    background-size: cover;
    position: relative;
    top: 0;
    .btn{
      @include btn('normal');
      display: inline-block;
      position: absolute;
      bottom: -25px;
      left: 17.5%;
    }
  }

</style>