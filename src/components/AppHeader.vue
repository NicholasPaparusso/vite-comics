<script>
  export default {
  name: 'AppHeader',

    data(){

      return{
        menu:[
          {
            text: 'characters',
            href: '#',
            current: false
          },

          {
            text: 'comics',
            href: '#',
            current: true
          },

          {
            text: 'movies',
            href: '#',
            current: false
          },

          {
            text: 'tv',
            href: '#',
            current: false
          },

          {
            text: 'games',
            href: '#',
            current: false
          },

          {
            text: 'cocllectibles',
            href: '#',
            current: false
          },

          {
            text: 'videos',
            href: '#',
            current: false
          },

          {
            text: 'fans',
            href: '#',
            current: false
          },

          {
            text: 'news',
            href: '#',
            current: false
          },

          {
            text: 'shop',
            href: '#',
            current: false
          },
        ]
      }

    }

  }
</script>

<template>

  <header>
    <div class="container">

      <div class="logo">
        <img src="/dc-logo.png" alt="">
      </div>

      <div class="nav">
        <ul>
          <li v-for="(link, index) in menu"
          :key="index">
          <a :class="{'active' : link.current}" :href="link.href">{{link.text}}</a></li>
        </ul>
      </div>

    </div>
  </header>

</template>


<style lang="scss" scoped>

@use '../styles/partials/variables' as *;
@use '../styles/partials/mixin' as *;

header{
  
  height: 120px;
  background-color: $secondary-color;
}

.container{
  @include d-flex('standard');
  justify-content: space-between;
  height: 100%;

  img{
    width: 80px;
  }

  ul{
    @include d-flex('standard');
    
    a{
      padding: 45px 25px;
      font-size: 0.9em;
      font-weight: 600;
       color: $text-color;
       &:hover,
       &.active{
        border-bottom: 5px solid $main-color;
        color: $main-color;
       }
    }
  }

}

</style>