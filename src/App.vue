<template>
  <section class="hero is-fullheight is-dark hero-image has-text-centered">
    <header class="navbar is-transparent is-fixed-top">
      <div class="container">
        <div id="navbarMenuHeroC" class="navbar-menu">
          <div class="navbar-end">
            <a class="navbar-item is-active">
              Home
            </a>
            <a class="navbar-item">
              About
            </a>
            <a class="navbar-item">
              Prices
            </a>
            <a class="navbar-item">
              Gallery
            </a>
            <a class="navbar-item">
              Team
            </a>
            <a class="navbar-item">
              Contact us
            </a>
            <a class="navbar-item">
              Our blog
            </a>
          </div>
        </div>
      </div>
    </header>
    <div class="hero-body">
      <div class="container">
        <h1 class="subtitle">
          Stay Flawless
        </h1>
        <h1 class="title is-size is-desktop hero-text">
          Flawless Cutz
        </h1>
        <h2 class="subtitle hero-text-sub has-text-grey-lighter">
          A Full-service Barber Shop
        </h2>
        <a
          class="button is-large is-dark is-inverted is-outlined"
          onclick=" window.open('https://flawlesscutz.barberly.online/','_blank')"
          >Book an appointment today</a
        >
      </div>
    </div>
  </section>

  <section class="body">
    <div class="container">
      <div class="columns">
        <div class="column is-12 is-offset-0">
          <div class="columns is-multiline">
            <div class="column is-12 post">
              <article class="columns">
                <div class="column is-7 post-img ">
                  <img src="./assets/images/barber-2.jpg" />
                </div>

                <div class="column is-5">
                  <div>
                    <h3 class="heading post-category">EST 2017</h3>
                    <h1 class="title post-title">Our history</h1>
                    <p class="post-excerpt">
                      Since 2017 Our History At Flawless Cutz Barbershop, we are
                      dedicated to providing an unparalleled hair styling and
                      grooming services that are tailored to each and every
                      client and their lifestyles; in an uplifting and inviting
                      atmosphere. As customers and clients are our only
                      priority, we value every single client that walks through
                      our door. Flawless Cutz Barbershop offers both style and a
                      community experience as a true "neighborhood shop".
                    </p>
                    <br />
                    <a href="#" class="button is-primary">Learn More</a>
                  </div>
                </div>
              </article>
            </div>
          </div>
          <br />
          <div class="columns is-multiline">
            <div
              class="column is-one-third"
              v-for="photo in photos"
              :key="photo.id"
            >
              <img :src="imageName(photo.img)" />
              <h3 class="heading post-category">{{ photo.category }}</h3>
              <h3 class="title post-title">{{ photo.title }}</h3>
              <div class="content">
                <p class="post-excerpt">{{ photo.content }}</p>
                <a>@{{ photo.author + " " }}</a>
                <a href="#">#{{ photo.tags1 + " " }}</a>
                <a href="#">#{{ photo.tags2 + " " }}</a>
              </div>
              <a href="#" class="button is-primary">Read More</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import photos from "@/photos.json";

export default {
  name: "App",
  components: {},
  data() {
    return {
      photos,
    };
  },
  setup() {
    return {
      showModal: false,
    };
  },
  methods: {
    imageName(filename) {
      return require(`./assets/images/${filename}`);
    },
  },
};
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.card {
  border-radius: 5px;
}
div.columns {
  padding: 5px;
  margin: 10px;
}
.hero-text {
  font-size: 10vw;
  font-family: "Merriweather", serif;
}

.hero-text-sub {
  font-size: 3vw;
  font-family: "Merriweather", serif;
}
.hero-image {
  background-image: url("./assets/images/barber-2.jpg");
  background-position: center center;
  background-repeat: no-repeat;
  background-size: cover;
  background-color: #999;
}
</style>
