<template v-if="gifs">
  <div class="w-11/12 float-right">
    <div v-for="gif in gifs" :key="gif">
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
