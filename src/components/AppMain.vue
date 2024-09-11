<script>
export default {
  data() {
    return {
      cards: [
  {
      thumb: "https://www.coverbrowser.com/image/action-comics/1-1.jpg",
      price: "$19.99",
      series: "Action Comics",
      type: "comic book",
  },
  {
      thumb: "https://www.panini.it/media/catalog/product/cache/a5b5dd3adfe0d321084804c738f29601/M/1/M1BLLA015ISBN_0.jpg",
      price: "$3.99",
      series: "American Vampire 1976",
      type: "comic book",
  },
  {
      thumb: "https://media.wired.com/photos/593384dad80dd005b42b2817/master/w_2560%2Cc_limit/Aquaman-16.jpg",
      price: "$16.99",
      series: "Aquaman",
      type: "graphic novel",
  },
  {
      thumb: "https://d29xot63vimef3.cloudfront.net/image/batgirl/1-1.jpg",
      price: "$2.99",
      series: "Batgirl",
      type: "comic book",
  },
  {
      thumb: "https://static.posters.cz/image/750/locandine-film-in-plexiglass-batman-prowl-comic-cover-i69653.jpg",
      price: "$3.99",
      series: "Batman",
      type: "comic book",
  },
  {
      thumb: "https://static.wikia.nocookie.net/marvel_dc/images/5/50/Batman_Beyond_v.1_1.jpg",
      price: "$2.99",
      series: "Batman Beyond",
      type: "comic book",
  },
  {
      thumb: "https://static.wikia.nocookie.net/marvel_dc/images/0/0d/Batman_Superman_Vol_1_1.jpg",
      price: "$3.99",
      series: "Batman/Superman",
      type: "comic book",
  },
  {
      thumb: "https://static.wikia.nocookie.net/marvel_dc/images/c/cf/Batman_Superman_Annual_Vol_2_1.jpg",
      price: "$4.99",
      series: "Batman/Superman Annual",
      type: "comic book",
  },
  {
      thumb: "https://static.wikia.nocookie.net/marvel_dc/images/5/54/Batman_The_Joker_War_Zone_Vol_1_1.jpg",
      price: "$5.99",
      series: "Batman: The Joker War Zone",
      type: "comic book",
  },
  {
      thumb: "https://static.wikia.nocookie.net/marvel_dc/images/6/64/Batman_Three_Jokers_Collected.jpg",
      price: "$6.99",
      series: "Batman: Three Jokers",
      type: "comic book",
  },
  {
      thumb: "https://static.wikia.nocookie.net/marvel_dc/images/f/f8/Batman_White_Knight_Presents_Harley_Quinn_Vol_1_1.jpg",
      price: "$4.99",
      series: "Batman: White Knight Presents: Harley Quinn",
      type: "comic book",
  },
  {
      thumb: "https://static.wikia.nocookie.net/marvel_dc/images/c/c8/Catwoman_Vol_2_1.jpg",
      price: "$16.99",
      series: "Catwoman",
      type: "graphic novel",
  },
]
    }
  }
}
</script>

<template>
  <main>
    <div class="jumbotron"></div>

    <div class="container">
      <div class="main-content">
        <div class="jumbobutton">
          <button>
            <a href="#">
              CURRENT SERIES
            </a>
          </button>
        </div>

        <div class="cards-container">
          <div v-for="(card, index) in cards" :key="index">
            <div class="seriesimage-container">
              <img :src="card.thumb" :alt="card.series">
            </div>

            <div>
              <p>{{ card.series }}</p>
            </div> 
          </div>
        </div>

        <div class="load-button">
          <button>
            <a href="#">
              LOAD MORE
            </a>
          </button>
        </div>   
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>

@use '../assets/scss/partials/mixins.scss' as *;
@use '../assets/scss/partials/variables' as *;

main {
    background-color: #1C1C1C;

    .jumbotron {
      min-height: 400px;
      width: 100%;
      background-image: url("../assets/img/jumbotron.jpg");
      background-size:cover;
    }

    .main-content {
      position: relative;
      padding: 60px 0 20px 0;

      .jumbobutton button {
        border: none;
        padding: 15px 30px;
        background-color: $mainColor;
        position: absolute;
        top: -25px;

        a {
          @include a-reset;
          font-size: 1.4rem;
        }
      }

      .cards-container {
          display: flex;
          flex-wrap: wrap;
          
          > * {
            width: 200px;
            margin: 0 auto;
            padding-bottom: 40px;
          }

          .seriesimage-container img {
            width: 190px;
            height: 190px;
            object-fit: cover;
            object-position: top;
          }

          p {
            padding: 15px 0;
            text-transform: uppercase;
            font-size: 0.9rem;
          }
      }

      .load-button {
        text-align: center;

        button {
          border: none;
          padding: 10px 60px;
          background-color: $mainColor;

          a {
            @include a-reset;
          }
        }
      }
    }
  }


</style>
