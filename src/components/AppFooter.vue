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
      ],

      socials: [
        {
          name: 'facebook',
          href: '#',
          img: 'footer-facebook.png'
        },

        {
          name: 'twitter',
          href: '#',
          img: 'footer-twitter.png'
        },

        {
          name: 'youtube',
          href: '#',
          img: 'footer-youtube.png'
        },

        
        {
          name: 'pinterest',
          href: '#',
          img: 'footer-pinterest.png'
        },

        
        {
          name: 'periscope',
          href: '#',
          img: 'footer-periscope.png'
        },
      ]
    }
  },

  methods:{
    getImagePath(imgName){
      return new URL(`../assets/img/${imgName}`, import.meta.url).href
    }
  }

  }
</script>

<template>

  <footer>

    <div class="top">

      <div class="container">

        
        <div class="links">
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

        <div class="logo"></div>

      </div>
    </div>

    <div class="bot">
      <div class="container">

        <div class="btn">
          SIGN-UP NOW!
        </div>

        <div class="socials">
          <h3>FOLLOW US</h3>

          <ul>
            <li v-for="(social,index) in socials"
            :key="index">
              <a :href="social.href">
                <img :src="getImagePath(social.img)" :alt="social.name">
              </a>
            </li>
          </ul>
        </div>

      </div>
    </div>

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
          height: 500px;
          width: 600px;
          background-image: url('../assets/img/dc-logo-bg.png');
          background-repeat: no-repeat;
          background-position: 0 -50px ;
        }
        
        .links{        
          padding: 20px 0;  
          display: flex;
          flex-wrap: wrap;
          max-width: 500px;
          position: relative;
          top: 0;
          .link-elements{
            padding: 0 25px;
            &:last-child{
               position: absolute;
               top: 249px;
            }
            
            h4{
              padding-bottom: 1em;
              color: $secondary-color
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
      }
    }

  .bot{
    height: 100px;
    background-color: $footer-color ;

    .container{
      height: 100%;
      @include d-flex('standard');
      justify-content: space-between;
      .btn{
        color: $secondary-color;
        padding: 14px 1.2em;
        border: 2px solid $main-color;
        cursor: pointer;
        &:hover{
          transform: scale(1.05);
        }
      }

      .socials{
        @include d-flex('standard');

        ul{
          @include d-flex('standard');

          li{
            padding: 10px;

            img{

              &:hover{
                filter: brightness(100);
              }

            }
          }
        }

        h3{
          margin-right: 20px ;
          font-size: 1.3em;
          color:  $main-color;
        }


      }
    }
  }
}

</style>