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
        },
      ]
    }
  },
  components: {
  },
  methods: {} 
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

  </main>

  <footer>

  </footer>
</template>

<style scoped>
  header {
    background-color: white;
    margin: 20px 0;
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
</style>
