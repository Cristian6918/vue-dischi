<template>
<div>
    <label for="filter">Filter By Genre</label>
    <select name="filter" @change='selectGenre($event)'>
        <option value="">All</option>
        <option v-for='genre in dinamicOption' :key="genre">{{genre}}</option>
       
    </select>
</div>
  
</template>

<script>
export default {
    name:'SelectComponent',
    data(){
        return {
            selected:''
        }
    },
    props:{dinamicOption:[]},
    methods:{
        selectGenre(event){
            this.selected=event.target.value;
            this.$emit('filterByGenre',this.selected);
           
        }
    }

}
</script>

<style  lang="scss" scoped>
@import '@/style/variables.scss';
label{
    color:white;
    padding:10px;
    border-radius:5px;
    margin:1rem;
   
}
select{
    outline: none;
    background-color:$secondary-color;
    color:white;
    border:none;
    padding:10px;
    border-radius:5px;
    

    &:hover{
         box-shadow: rgba(0, 0, 0, 0.15) 0px 15px 25px, rgba(0, 0, 0, 0.664) 0px 5px 10px;

    }
    
   
    
}

</style>