<script>
  export default {
  name: 'AppFooter',

  data(){
    return{
      links: [
        {
          title: 'dc comics',
          linkList: ['Characters','Comics','Movies','TV','Games','Videos','News'],
        },

        {
          title: 'dc',
          linkList: ['Terms Of Use','Privacy policy(New)','Ad Choises','Advertising','Jobs','Subscriptions','Talent Workshops','CPSC Certificates','Ratings','Shop Help','Contact Us'],
        },

        {
          title: 'sites',
          linkList: ['DC','MAD Magazine','DC Kids','DC Universe','DC Power Visa'],
        },

        {
          title: 'shop',
          linkList: ['Shop DC','Shop DC Collectibles'],
        },
      ]
    }
  }
  }
</script>

<template>

  <footer>

    <div class="top">
      <div class="container">

        <div v-for="(linkEl,index) in links"
        :key="index"
        class="link-elements">
          <h4>{{linkEl.title}}</h4>
          <ul>
            <li></li>
          </ul>
        </div>

        <div class="logo">
          
        </div>

      </div>
    </div>

    <div class="bot"></div>

  </footer>

</template>


<style lang="scss" scoped>

@use '../styles/partials/variables' as *;
@use '../styles/partials/mixin' as *;

footer{
  height: calc(100vh - (120px + 160px + 140px));
  background-image: url('../assets/img/footer-bg.jpg') ;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
  z-index: -2;
  overflow: hidden;
  .top{
    height: calc(100% - 100px);
    @include d-flex('standard');
      position: relative;
      z-index: -1;

    .logo{
      height: 600px;
      background-image: url('../assets/img/dc-logo-bg.png');
      background-repeat: no-repeat;
      background-size: contain ;
      
    }
  }
  .bot{
    height: 100px;
    background-color: $footer-color ;
  }
}

</style>