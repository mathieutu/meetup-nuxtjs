<template>
  <div>
    <nav>
        <nuxt-link to="/">Home</nuxt-link>
        <nuxt-link to="/about">About</nuxt-link>
        <nuxt-link to="/counter">Counter</nuxt-link>
    </nav>
    <div class="container">
      <nuxt/>
    </div>
  </div>
</template>

<style lang="scss">
html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

nav, .container {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;

  a {
    margin: 10px;
    &.nuxt-link-exact-active {
      font-weight: bolder;
    }
  }
}

.container {
  min-height: 100vh;
}
</style>
