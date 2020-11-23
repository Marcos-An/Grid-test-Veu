<template>
  <span>
    <h1 :style="{color: user.background !== 'white' ? 'white' : 'black'}">{{user.title}}</h1>
    <p :style="{color: user.text}">{{user.message}}"</p>
  </span>
</template>

<script>
export default {
  props: ['user']
}
</script>
<style scoped>
  h1{
    text-align: left;
    font-weight: 600;
    font-size: 1.5rem;
    margin: 20px 0px
  }
  p{
    text-align: left;
    font-size: 1.1rem;
    margin: 20px 0px
  }
</style>