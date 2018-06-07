<template>
  <div>
    <p>Total count : <strong v-text="$store.state.count"/></p>
    <button @click="$store.commit('decrement')">-</button>
    <button @click="$store.commit('increment')">+</button>
  </div>
</template>

<script>
// import Component from './Component';

export default {};

</script>

<style lang="scss" scoped>

</style>
