<template>
  <div class=" container-fluid ct-main ">
    
      <div v-if='albums.length > 0'  >
          <SelectComponent :dinamicOption='optionGenre' @filterByGenre='filterSelect'/>
          <div class="  row  align-items-scretch justify-content-evenly ct-h90  ct-card-container ">
            <CardContent v-for='album in filteredList' :key='album.name +album.author' :album='album' />   
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
import SelectComponent from '@/components/SelectComponent.vue';

export default {
    name:'MainComponent',
   
    
          
    data(){
      return {
        albums:[],
        optionGenre:[],
        albumGenre:''
      }
    },
    props:{
      url:String
    },
    computed:{
      filteredList(){
        return this.albums.filter((item)=>item.genre.includes(this.albumGenre))
      }
    },
     components:{CardContent,LoaderComponent,SelectComponent},
    mounted(){
      this.loadData();
    
      
     
      
     
      
    },
    methods:{
      loadData(){
        axios.get(this.url).then((response)=>{
          if(response.status===200){
            this.albums=response.data.response;
            this.albums.forEach(element=>{
	if(!this.optionGenre.includes(element.genre)){
		this.optionGenre.push(element.genre);
   
	}
});
          }
        })
        
      },
      filterSelect(albumGenre){
        this.albumGenre=albumGenre;
        
        
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