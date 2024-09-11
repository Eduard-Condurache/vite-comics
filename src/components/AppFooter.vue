<script>
export default {
  data() {
    return {
      footerlinks: [
        {
          label: 'DIGITAL COMICS',
          url: '#',
          icon: 'buy-comics-digital-comics.png'
        },
        {
          label: 'DC MERCHANDISE',
          url: '#',
          icon: 'buy-comics-merchandise.png'
        },
        {
          label: 'SUBSCRIPTION',
          url: '#',
          icon: 'buy-comics-subscriptions.png'
        },
        {
          label: 'COMIC SHOP LOCATOR',
          url: '#',
          icon: 'buy-comics-shop-locator.png'
        },
        {
          label: 'DC POWER VISA',
          url: '#',
          icon: 'buy-dc-power-visa.svg'
        },   
      ],
      footerinfos: [
        {
          title: 'DC COMICS',
          url: '#',
          infos: [
            'Characters',
            'Comics',
            'Movies',
            'Tv',
            'Games',
            'Videos',
            'News',
          ]
        },
        {
          title: 'DC',
          url: '#',
          infos: [
            'Terms Of Use',
            'Privacy policy (New)',
            'Ad Choices',
            'Advertising',
            'Jobs',
            'Subscriptions',
            'Talent Workshops',
            'CPSC Certificates',
            'Ratings',
            'Shop Help',
            'Contact Us',
          ]
        },
        {
          title: 'SITES',
          url: '#',
          infos: [
            'DC',
            'MAD Magazine',
            'DC Kids',
            'DC Universe',
            'DC Power Visa',
          ]
        },
        {
          title: 'SHOP',
          url: '#',
          infos: [
            'Shop DC',
            'Shop DC Collectibles',
          ]
        }
      ]
    }
  },
  methods: {
    getImagePath: function(img) {
      const url = new URL(`../assets/img/${img}`, import.meta.url);

      const link = url.href
      return link
    }
  }
}
</script>

<template>

<footer>
    <div class="footer-links">
      <div class="container">
        <div>
          <ul>
              <li v-for="(footerlink, index) in footerlinks" :key="index">
                <img :src="getImagePath(footerlink.icon)" :alt="footerlink.label">
                <a :href="footerlink.url">
                {{ footerlink.label }}
                </a>
              </li>
            </ul>
        </div>
      </div>
    </div>

    <div class="footer-infos-bg">
      <div class="container">
        <div class="footer-infos">
          <div v-for="(list, index) in footerinfos" :key="index">
            <ul>
              <h4>{{ list.title }}</h4>
              <li v-for="(info, index) in list.infos" :key="index">
                <a :href="list.url">
                  {{ info }}
                </a>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>

    <div class="footer-socials">
      <div class="container">
        <div>
          <button>
            <a href="#">
              SIGN-UP NOW
            </a>
          </button>
        </div>

        <div class="socials">
          <h2>
            FOLLOW US
          </h2>

          <div class="social-icons">
            <a href="#">
              <img src="../assets/img/footer-facebook.png" alt="facebook">
            </a>
            <a href="#">
              <img src="../assets/img/footer-twitter.png" alt="twitter">
            </a>
            <a href="#">
              <img src="../assets/img/footer-youtube.png" alt="youtube">
            </a>
            <a href="#">
              <img src="../assets/img/footer-periscope.png" alt="periscope">
            </a>
            <a href="#">
              <img src="../assets/img/footer-pinterest.png" alt="pinterest">
            </a>
          </div>
        </div>
      </div>
    </div>
  </footer>

</template>

<style lang="scss" scoped>

@use '../assets/scss/partials/mixins.scss' as *;
@use '../assets/scss/partials/variables' as *;

  /* FOOTER LINKS */

  footer .footer-links {
    padding: $yPadding;
    background-color: $mainColor;
    img {
      max-width: 50px;
    }

    ul {
    width: 100%;
    @include simple-ul;
    @include flex-center;

    li {
      @include flex-center;
      a {
        margin: $xMargin;
        @include a-reset;
        white-space: nowrap;
      }
    }
    }
  }

  /* FOOTER INFOS */

  footer .footer-infos-bg {
  padding: $yPadding;
  background-image: 
    url('src/assets/img/dc-logo-bg.png'),
    url('src/assets/img/footer-bg.jpg');
  background-position: 75% center, center;
  background-size: 500px, cover;
  background-repeat: no-repeat, no-repeat;
}

  footer .footer-infos {
    width: 40%;
    height: 80%;
    display: flex;
    flex-wrap: wrap;

    h4 {
    margin-bottom: 10px;
    font-size: 1.2rem;
  }

    ul {
      @include simple-ul;
      margin-right: 30px;

      li {
      padding: 0;

        a {
        text-decoration: $noTextDecoration;
        color: grey;
        font-size: 0.85rem;
        }
      }
    }
  }

  /* FOOTER SOCIALS */

  footer .footer-socials {
    background-color: #303030;

    .container {
      @include flex-center;
      padding: $yPadding;

      button {
        padding: 15px 20px;
        background-color: #303030;
        border: 2px solid $mainColor;
        font-weight: bold;
        font-size: 1.1rem;

        a {
          @include a-reset;
        }
      }

      .socials {
        display: flex;
        
        h2 {
          margin-right: 20px;
          color: $mainColor;
        }
      }

      .social-icons img {
        margin: $xMargin;
      }
    }   
  }

</style>
