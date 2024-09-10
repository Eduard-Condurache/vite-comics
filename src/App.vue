<script>

import AppHeader from './components/AppHeader.vue';

export default {
  data() {
    return {
      navlinks: [
        {
          label: 'CHARACTERS',
          url: '#',
          active: false
        },
        {
          label: 'COMICS',
          url: '#',
          active: true
        },
        {
          label: 'MOVIES',
          url: '#',
          active: false
        },
        {
          label: 'TV',
          url: '#',
          active: false
        },
        {
          label: 'GAMES',
          url: '#',
          active: false
        },
        {
          label: 'COLLECTIBLES',
          url: '#',
          active: false
        },
        {
          label: 'VIDEOS',
          url: '#',
          active: false
        },
        {
          label: 'FANS',
          url: '#',
          active: false
        },
        {
          label: 'NEWS',
          url: '#',
          active: false
        },
        {
          label: 'SHOP',
          url: '#',
          active: false
        }
      ],
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
  components: {
  },
  methods: {
    getImagePath: function(img) {
      const url = new URL(`../assets/img/${img}, import.meta.url`);

      const link = url.href;

      return link;
    }
  } 
}
</script>

<template>
  <header>
    <div class="container">
      <nav>
        <div class="logo">
          <img src="./assets/img/dc-logo.png" alt="logo">
        </div>

        <div>
          <ul>
            <li v-for="(link, index) in navlinks" :key="index">
              <a :href="link.url" :class="{
                'active': link.active
              }">
              {{ link.label }}
              </a>
            </li>
          </ul>
        </div>
      </nav>
    </div>
  </header>

  <main>
    <div class="container">
      <div>
        <h1>
          --&gt; Content goes here &lt;--
        </h1>
      </div>
    </div>
  </main>

  <footer>
    <div class="footer-links">
      <div class="container">
        <div>
          <ul>
              <li v-for="(footerlink, index) in footerlinks" :key="index">
                <img src="./assets/img/buy-comics-merchandise.png" :alt="footerlink.label">
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
            SIGN-UP NOW
          </button>
        </div>

        <div class="socials">
          <h2>
            FOLLOW US
          </h2>

          <div class="social-icons">
            <img src="./assets/img/footer-facebook.png" alt="facebook">
            <img src="./assets/img/footer-facebook.png" alt="facebook">
            <img src="./assets/img/footer-facebook.png" alt="facebook">
            <img src="./assets/img/footer-facebook.png" alt="facebook">
            <img src="./assets/img/footer-facebook.png" alt="facebook">
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
  /* HEADER */
  header {
    background-color: white;
    height: 150px;
    display: flex;
    align-items: center;
  }

  header nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  header nav ul {
    display: flex;
    list-style: none;
  }

  header nav ul li a {
    text-decoration: none;
    margin: 0 10px;
  }

  /* MAIN */

  main {
    width: 100%;
    height: 150px;
    background-color: lightcoral;
    display: flex;
    align-items: center; /* Centers vertically */
  }

  /* FOOTER */

  footer .footer-links {
    padding: 40px 0;
    background-color: #0282F9;
  }

  footer .footer-links ul {
    display: flex;
  }

  footer .footer-links ul li {
    display: flex;
    align-items: center;
  }
  
  footer .footer-infos-bg {
  padding: 40px 0;
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
  }

  footer .footer-infos ul {
    list-style: none;
    padding: 0;
    margin-right: 30px;
  }

  footer .footer-infos ul li {
    padding: 0;
  }

  footer .footer-infos ul li a {
    text-decoration: none;
    color: grey;
    font-size: 0.85rem;
  }

  footer .footer-infos h4 {
    margin-bottom: 10px;
    font-size: 1.2rem;
  }

  footer .footer-socials {
    background-color: #303030;
  }

  footer .footer-socials .container {
    display: flex;
    padding: 40px 0;
    justify-content: space-between;
  }

  footer .footer-socials .container button {
    border: none;
    padding: 20px;
  }

  footer .footer-socials .socials {
    display: flex;
  }
</style>
