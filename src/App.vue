<template>
  <div id="app">
    <HeaderComponent />
    <MainComponent :url='apiUrl' />
    
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from '@/components/MainComponent.vue';


export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent
  },
  data(){
    return{
      apiUrl:'https://flynn.boolean.careers/exercises/api/array/music'

    }
  }
}
</script>


<style lang="scss" >

@import 'style/common.scss';



#app {
  
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  min-height:100vh;
  display:flex;
  flex-direction:column;

}
</style>
