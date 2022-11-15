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

        <div class="left-menu">
                  
        <div v-for="(linkEl,index) in links"
        :key="index"
        class="link-elements">
          <h4>{{linkEl.title.toUpperCase()}}</h4>
          <ul>
            <li v-for="(link, index) in linkEl.linkList"
            :key="index"><a href="">{{link}}</a></li>
          </ul>
        </div>

        </div>

        <div class="logo">
          <img src="../assets/img/dc-logo-bg.png" alt="">
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
  
  height: calc(100VH - (120px + 140px + 160px));

  .top{
    height: calc(100% - 100px);
    background-image: url('../assets/img/footer-bg.jpg') ;
    background-repeat: no-repeat;
    background-size: cover;
    overflow: hidden;
   
      .container{
        display: flex;
        justify-content: space-between;

        .logo{
          overflow: hidden;
        }
        
        .left-menu{
          padding: 20px 0;
          display: flex;
          flex-wrap: wrap;
          max-width: 600px;
          .link-elements{
            display: inline-block;
            padding: 0 20px;
            
            h4{
              padding-bottom: 1em ;
            }

            a{
              color:  darken($color: $secondary-color, $amount: 50);
              font-size: .8em;
              line-height: 2em;

              &:hover{
                color: $secondary-color;
              }
            }
            
          }
        }
         
        img{
          object-position: 0 -50px;
        }


        h4{
           color: $secondary-color;
          }
      }


  }
  .bot{
    height: 100px;
    background-color: $footer-color ;
  }
}

</style>