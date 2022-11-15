<script>
  export default {
  name: 'AppMain',
  }
</script>

<template>

<main>
    <div class="container">
      <h1>
        Pagina in stato di manutenzione .. scusate l'inconveniente
      </h1>
    </div>    
  </main>

</template>


<style lang="scss" scoped>
  @use '../styles/partials/variables' as *;
  @use '../styles/partials/mixin' as *;

  main{
    background-color: black;
    color: $secondary-color;
    .container{
      height: 140px;
      @include d-flex('standard')
    }
  }

</style>