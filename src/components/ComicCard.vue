  <script>
  export default {
    name: 'ComicCard',
    props:{
      image: String,
      title: String,  
      price: String,
      type: String
    }
  }
  </script>

<template>
 

    <div class="card">
      <div class="image">
        <img :src="image" alt="">
        <div class="info-hidden">
          <p>Prezzo: {{price}}</p>
          <p>Tipologia: {{type}}</p>
        </div>
      </div>
      
      <div class="info">
        <h4>{{title}}</h4>
      </div>
    </div>


</template>


<style lang="scss" scoped>

@use '../styles/partials/variables' as *;
    .card{
      width: calc((100% / 6) - 20px);
      margin: 10px 10px;
      color: $secondary-color ;
     
      .image{
        cursor: pointer;
        position: relative;
        top: 0;

        &:hover .info-hidden{
          opacity: 100;
          transition: all 1s linear;
        }

        img{
        height: 250px;
        object-fit:cover;
        object-position:top;
      }
      }

      .info{
        padding: 5px;
        font-size: 1.1em;
      }

      .info-hidden{
        font-size: .8em;
        width: 100%;
        background-color: $main-color;
        padding: 5px;
        position: absolute;
        bottom: 7%;
        opacity: 0;
      }
    }


</style>