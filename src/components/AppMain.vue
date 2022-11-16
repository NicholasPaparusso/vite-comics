<script>

  import ComicCard from './ComicCard.vue';
  import  comics  from '../data/comics.js';

  export default {
    name: 'AppMain',
    data(){
      return{
        comics,
      }
    },

  components:{
    ComicCard ,
  } 

  }
</script>

<template>

<main>
    <div class="container">
      <ComicCard v-for="(comic, index) in comics"
      :key="index"
      :image="comic.thumb"
      :title="comic.series"  
      :price="comic.price"
      :type="comic.type"
      />

      <div class="btn">
        <h5>load more</h5>
      </div>
    </div>    
  </main>

</template>


<style lang="scss" scoped>
  @use '../styles/partials/variables' as *;
  @use '../styles/partials/mixin' as *;

  main{
    background-color: $main-bg-color;
    color: $secondary-color;
    .container{
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      padding: 50px 0;

      .btn{
        @include btn('small');
        justify-self: center;
      }
    }
  }

</style>