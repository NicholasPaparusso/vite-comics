<script>
  export default {
  name: 'AppMenu',

  data(){
    return{
      items:[
        {
          text: 'digital comics',
          img: 'buy-comics-digital-comics.png',
          href: '#'
        },
        
        {
          text: 'dc merchandise',
          img: 'buy-comics-merchandise.png',
          href: '#'
        },

        {
          text: 'subscription',
          img: 'buy-comics-subscriptions.png',
          href: '#'
        },


        {
          text: 'comic shop locator',
          img: 'buy-comics-shop-locator.png',
          href: '#'
        },

        {
          text: 'dc power visa',
          img: 'buy-dc-power-visa.svg',
          href: '#'
        },

      ]
    }
  },
  methods:{
    getImage(imgName){
      return new URL(`../assets/img/${imgName}`, import.meta.url).href
    }
  },
  }
</script>

<template>
  <div class="menu">
    <div class="container">

      <div v-for="(item, index) in items"
      :key="index"
      class="card">
        <img :src="getImage(item.img)" :alt="item.text">
        <a :href="item.href" >{{item.text.toUpperCase()}}</a>
      </div>
    </div>

  </div>
</template>


<style lang="scss" scoped>

@use '../styles/partials/variables' as *;
@use '../styles/partials/mixin' as *;
  .menu{
    background-color: $main-color ;
  }

  .container{
    height: 160px;
    @include d-flex('center');
    gap: 80px;
    .card{
      @include d-flex('standard');

      img{
      width: 50px;
      margin-right: 10px;
      cursor: pointer;

      &:hover{
        transform: scale(1.05);
        transition: all .5s linear;
      }

      }
      a{
        color: $secondary-color;
        font-size: .9em;
        &:hover{
          text-decoration: underline;
        }
      }
    }
  }

</style>