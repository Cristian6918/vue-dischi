<template>
  <div class=" container-fluid ct-main ">
    
      <div v-if='albums.length > 0'  >
        <div class="  row  align-items-scretch justify-content-evenly ct-h90  ct-card-container ">
        <CardContent v-for='album in albums' :key='album.name +album.author' :album='album' />   
        </div>    
        </div>
        <div v-else>
          <LoaderComponent/>
        
      </div>
  </div>
</template>

<script>

import axios from 'axios';
import CardContent from '@/components/CardContent.vue';
import LoaderComponent from '@/components/LoaderComponent.vue';

export default {
    name:'MainComponent',
   
    
          
    data(){
      return {
        albums:[]
      }
    },
    props:{
      url:String
    },
     components:{CardContent,LoaderComponent},
    mounted(){
      this.loadData();
    },
    methods:{
      loadData(){
        axios.get(this.url).then((response)=>{
          console.log(response.data);
          if(response.status===200){
            this.albums=response.data.response;
            console.log(this.albums[0]);
          }

        })
      }
    }

}
</script>

<style lang='scss' scoped>
@import '@/style/variables.scss';

.ct-main{
  width:100%;
    background-color: $main-bg-color;
    flex-grow:1;
   
   
}
.ct-card-container{
  width:70%;
  margin: auto;
 margin-top:5vh;
 
 
}


</style>