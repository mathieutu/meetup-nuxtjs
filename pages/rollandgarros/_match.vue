<template>
  <div>
    <ul>
      <li>
        nuxt-link:
        <nuxt-link :to="next" v-text="next"/>
      </li>
      <li>
        a href: <a :href="next" v-text="next"/>
      </li>
    </ul>
    <p v-for="player of teamA.players" :key="player.shortName">
      {{player.firstName}} {{player.lastName}}
    </p>
    <p v-for="player of teamB.players" :key="player.shortName">
      {{player.firstName}} {{player.lastName}}
    </p>
  </div>
</template>

<script>

export default {
  async asyncData({$axios, params}) {
    const {data: {match}} = await $axios.get(`https://www.rolandgarros.com/api/en-us/matches/${params.match}`);
    return match;
  },
  mounted() {
    window.addEventListener("beforeunload", function (e) {
      console.warn('You\'re leaving the page!');
    });
  },
  computed: {
    next() {
      return this.$route.path.slice(0, -3) + String((Number(this.$route.path.slice(-3)) + 1)).padStart(3, "0");
    },
  }
};
</script>
