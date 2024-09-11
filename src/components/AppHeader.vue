<script>
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
      activeLink: 1
    };
  },
  methods: {
    setActiveLink(newIndex) {
      this.activeLink = newIndex;
    }
  }
}
</script>

<template>
  <header>
    <div class="container">
      <nav>
        <div class="logo">
          <img src="../assets/img/dc-logo.png" alt="logo">
        </div>

        <div>
          <ul>
            <li v-for="(link, index) in navlinks" :key="index">
              <a :href="link.url" 
              :class="{'active': activeLink === index}"
              @click.prevent="setActiveLink(index)">
              {{ link.label }}
              </a>
            </li>
          </ul>
        </div>
      </nav>
    </div>
  </header>
</template>

<style lang="scss" scoped>

@use '../assets/scss/partials/mixins.scss' as *;
@use '../assets/scss/partials/variables' as *;

  header {
    background-color: white;
    height: 150px;
    @include flex-center;
    margin-top: 20px;

    nav {
      @include flex-center;
      align-items: center;

      ul {
        display: flex;
        @include simple-ul;

        li a {
          text-decoration: $noTextDecoration;
          margin: $xMargin;
          font-size: 0.90rem;
          color: #464646;
          font-weight: bold;
          position: relative;

          &.active {
            color: $mainColor;
            
            &::after {
              content: '';
              position: absolute;
              left: 0;
              right: 0;
              bottom: -65px;
              height: 5px;
              background-color: $mainColor;
            }
          }
        }
      }
    }
  }

</style>
