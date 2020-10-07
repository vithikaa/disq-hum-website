<template>
  <div class="home">
    <header>
      <ul id="dropdown1" class="dropdown-content">
        <li><a href="#!">one</a></li>
        <li><a href="#!">two</a></li>
        <li class="divider"></li>
        <li><a href="#!">three</a></li>
      </ul>

      <nav class="white">
        <div class="nav-wrapper container">
          <a class="blue-text brand-logo" href="#">Logo</a>
          <ul id="nav-mobile" class="right hide-on-med-and-down">
            <li><a class="blue-text" href="sass.html">Sass</a></li>
            <li><a class="blue-text" href="badges.html">Components</a></li>
            <li><a class="blue-text" href="collapsible.html">JavaScript</a></li>
            <li>
              <a
                class="blue-text dropdown-trigger"
                href="#!"
                data-target="dropdown1"
                >Dropdown<i class="material-icons right">arrow_drop_down</i></a
              >
            </li>
          </ul>
        </div>
      </nav>
    </header>
    <main>
      <div class="carousel carousel-slider">
        <a class="carousel-item" href="#one!"
          ><img src="https://lorempixel.com/800/400/food/1"
        /></a>
        <a class="carousel-item" href="#two!"
          ><img src="https://lorempixel.com/800/400/food/2"
        /></a>
        <a class="carousel-item" href="#three!"
          ><img src="https://lorempixel.com/800/400/food/3"
        /></a>
        <a class="carousel-item" href="#four!"
          ><img src="https://lorempixel.com/800/400/food/4"
        /></a>
      </div>


      <section class="section">
        <div class="container">
          <div class="row">
            <div class="col s12 m6 l4">
              <div class="card-panel">
                card
              </div>
            </div>
            <div class="col  s12 m6 l4">
              <div class="card-panel">
                card
              </div>
            </div>
            <div class="col  s12 m6 l4">
              <div class="card-panel">
                card
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
// @ is an alias to /src
import M from 'materialize-css'
export default {
  name: 'Home',
  components: {},
  data() {
    return {
      carousel: null
    }
  },

  mounted() {
    M.AutoInit()
    var elem = document.querySelector('.carousel')
    this.carousel = M.Carousel.init(elem, {
      fullWidth: true,
      indicators: true
    })
    this.autoplay()
    M.Dropdown.init(document.querySelectorAll('.dropdown-trigger'), {
      hover: true,
      constrainWidth: false,
      coverTrigger: false
    })
  },

  methods: {
    autoplay() {
      this.carousel.next()
      setTimeout(this.autoplay, 6000)
    }
  }
}
</script>
