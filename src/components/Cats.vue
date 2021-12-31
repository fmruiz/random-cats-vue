<template>
  <h1>{{ title }}</h1>
  <img :src="imgCats" />
</template>

<script>
export default {
  data() {
    return {
      title: "Random Cats!",
      imgCats: null,
    };
  },
  methods: {
    async getRandomCats() {
      const { status, url } = await fetch("https://cataas.com/cat/gif");

      if (status !== 200) return;

      this.imgCats = url;
    },
  },
  beforeMount() {
    this.getRandomCats();
  },
};
</script>

<style></style>
