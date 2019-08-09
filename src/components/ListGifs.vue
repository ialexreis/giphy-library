<template v-if="gifs">
  <div class="flex flex-wrap -mx-3 overflow-hidden sm:-mx-2 md:-mx-1 lg:-mx-px xl:-mx-2 float-right container_margin">
    <div class="my-3 px-3 w-1/3 overflow-hidden sm:my-2 sm:px-2 sm:w-1/3 md:my-1 md:px-1 md:w-1/3 lg:my-px lg:px-px lg:w-1/3 xl:my-2 xl:px-2 xl:w-1/4" v-for="gif in gifs" :key="gif">
      <figure class="gif-figure red" @mouseenter="toggleHover" @mouseleave="toggleHover" :class="addHover">
        <img class="object-cover gif-image" :src="gif.images.original.url" alt="sample28" />
        <h3 v-if="gif.user">{{ gif.user.display_name }}</h3>
        <div class="icons">
          <a :href="`${facebookShare}${gif.images.original.url}`" target="_blank"><span class="icon-facebook-logo"></span></a>
          <a :href="`${linkedinShare}${gif.images.original.url}`" target="_blank"><span class="icon-linkedin-logo"></span></a>
          <a :href="`${twitterShare}${gif.images.original.url}`" target="_blank"><span class="icon-twitter"></span></a>
          <a :href="`${googleShare}${gif.images.original.url}`" target="_blank"><span class="icon-google-plus"></span></a>
        </div>
        <div class="plus-icon">
          <a href=""><span class="icon-zoom-tool"></span></a>
        </div>
        <div class="corner"><span class="icon-plus"></span></div>
      </figure>
    </div>
  </div>


</template>


<script>
export default {
  name: "ListGifs",

  data() {
    return {
      isHover: false,
      gifs: null,
      apiURL: process.env.VUE_APP_GIPHY_URL,
      apiKey: process.env.VUE_APP_API_KEY,
      facebookShare: process.env.VUE_APP_FACEBOOK,
      linkedinShare: process.env.VUE_APP_LINKEDIN,
      googleShare: process.env.VUE_APP_GOOGLE,
      twitterShare: process.env.VUE_APP_TWITTER 
    };
  },

  methods: {
    fetchGifs: function() {
      const url = `${this.apiURL}trending?api_key=${this.apiKey}`;
      fetch(url)
        .then(response => response.json())
        .then(gifResponse => (this.gifs = gifResponse.data));
    },
    toggleHover: function() {
      this.isHover = this.isHover
    },
  },

  computed: {
     addHover: function() {
      return {
        'hover': this.isHover
      }
    }
  },

  created: function() {
    this.fetchGifs();
  }
};
</script>
