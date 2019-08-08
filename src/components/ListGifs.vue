<template v-if="gifs">
  <div class="flex flex-wrap -mx-3 overflow-hidden sm:-mx-2 md:-mx-1 lg:-mx-px xl:-mx-2 float-right">
    <div class="my-3 px-3 w-1/3 overflow-hidden sm:my-2 sm:px-2 sm:w-1/3 md:my-1 md:px-1 md:w-1/3 lg:my-px lg:px-px lg:w-1/3 xl:my-2 xl:px-2 xl:w-1/4" v-for="gif in gifs" :key="gif">
      <a :href="gif.url">
        <img class="gif-image" :src="gif.images.original.url" />
      </a>
    </div>
  </div>


</template>


<script>
export default {
  name: "ListGifs",

  data() {
    return {
      gifs: null,
      apiURL: process.env.VUE_APP_GIPHY_URL,
      apiKey: process.env.VUE_APP_API_KEY
    };
  },

  methods: {
    fetchGifs: function() {
      const url = `${this.apiURL}trending?api_key=${this.apiKey}`;
      fetch(url)
        .then(response => response.json())
        .then(data => (this.gifs = data.data));
    }
  },

  created: function() {
    this.fetchGifs();
  }
};
</script>
