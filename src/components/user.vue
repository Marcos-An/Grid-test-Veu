<template>
  <span>
    <div class="avatar" :style="{backgroundImage: `url('${user.avatar}')`}"/>
    <div class="infos">
      <h3 :style="{color: user.background !== 'white' ? 'white' : 'black'}">{{user.name}}</h3>
      <h4 :style="{color: user.text}">{{user.status}}</h4>
    </div>
  </span>
</template>

<script>
export default {
  props: ['user']
}
</script>
<style scoped>
  span{
    display: flex;
  }
  .avatar {
    height: 40px;
    width: 40px;
    border: 2px solid #eaeeee;
    border-radius: 100%;
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center
  }
  .infos{
    margin-left: 25px;
    text-align: left;
  }
  .infos h3{
    color: white;
    font-weight: 500;
    font-size: 1.1rem;
    margin: 0
  }
  .infos h4{
    color: white;
    font-weight: 200;
    font-size: 1rem;
    margin: 0
  }
</style>