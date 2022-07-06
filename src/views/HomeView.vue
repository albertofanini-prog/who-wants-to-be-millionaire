<template>
  <div class="home" :style="background">
    <img class="logo" alt="Millionaire logo" src="../assets/logo_1.png">
    <QuizBox/>
  </div>
</template>

<script>
import QuizBox from '@/components/QuizBox.vue'

export default {
  name: 'HomeView',
  data(){
    return{
      background:{
        backgroundImage: "url(https://image.api.playstation.com/vulcan/img/rnd/202111/3009/Icu3kOAJ00NPRiMtiBKVsV0z.png)",
      }
    }
  },
  components: {
    QuizBox
  }
}
</script>

<style lang="scss">
  .home{
    // border: 3px solid orange;
    width: 100%;
    height: 100%;
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
    .logo{
      height: 22%;
    }
  }
</style>
