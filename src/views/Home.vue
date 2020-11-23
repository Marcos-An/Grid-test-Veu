<template>
  <div id="container">
        <div class="home">
          <div v-for="(user, index) in users" :key="index" :style="{backgroundColor: user.background}">
            <User :user="user" />
            <Content :user="user"/>
          </div>
        </div>
  </div>
</template>

<script>
import user from '../services/users'
import User from '../components/user'
import Content from '../components/content'

export default {
  name: 'Home',
  data() {
    return {
      users: user.users
    }
  },
  components: {
    User: User,
    Content: Content
  }
}
</script>

<style scoped>
  #container {
    height: 100vh;
    width: 100vw;
    background-color:#edf2f9;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  
  .home {
    display: grid;
    gap: 1.5vw;
    padding: 0vw 15vw;
    grid-template-areas: "purple purple purple gray white2"
                         "white1 blue blue blue white2";
  
  }
 @media (max-width: 600px) {
   .home {
     gap: 15vw;
     padding: 10vw 5vw;
      grid-template-areas: "purple"
                            "gray"
                            "white1"
                            "blue"
                            "white2";
   }
   .home div:nth-child(1) {
    grid-area: purple;
    background-image: url('/assets/bg-pattern-quotation.svg');
    background-repeat: no-repeat;
    background-position: 90% 0px !important; 
    background-size: 75px !important;
  }
  #container {
    height: 100%;
  }
  };

  .home div {
    border-radius: 10px;
    padding: 30px;
    box-shadow: 27px 26px 32px -29px rgba(0,0,0,0.29);
  }
  
  .home div:nth-child(1) {
    grid-area: purple;
    background-image: url('/assets/bg-pattern-quotation.svg');
    background-repeat: no-repeat;
    background-position: 80% 0px; 
    background-size: 125px
  }
  .home div:nth-child(2) {
    grid-area: gray;
  }

  .home div:nth-child(3) {
    grid-area: white1;
  }

  .home div:nth-child(4) {
    grid-area: blue;
  }
  .home div:nth-child(5) {
    grid-area: white2;
  }
</style>