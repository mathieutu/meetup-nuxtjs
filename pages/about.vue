<template>
    <div>
      <p>Serving from <strong v-text="from"/> for <strong v-text="userAgent"/></p>
      <p>The count is <strong v-text="$store.state.count"/></p>

    </div>
</template>

<script>

export default {
    asyncData({req, isStatic}) {
        return {
            userAgent: req ? req.headers['user-agent'] : navigator.userAgent,
            from: isStatic ? 'static' : process.client ? 'client' : 'server'
        };
    }
};

</script>

<style scoped>
</style>
