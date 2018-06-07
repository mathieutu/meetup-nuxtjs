<template>
    <div>
      <p>Serving from <strong v-text="from"/> for <strong v-text="userAgent"/></p>
      <nuxt-link to="/">Home</nuxt-link>

    </div>
</template>

<script>

export default {
    asyncData({req, isClient}) {
        return {
            userAgent: req ? req.headers['user-agent'] : navigator.userAgent,
            from: isClient ? 'client' : 'server'
        };
    }
};

</script>

<style scoped>
</style>
