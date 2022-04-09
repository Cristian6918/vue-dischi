<template>
  <div class=" row ct-card m-2 col-10 col-lg-3 col-xl-2 col-md-4 align-items-start">
      <div class="image-container ">
          <img :src="album.poster" :alt="album.name + album.author + album.year + album.title ">
      </div>
      <div class="text-container">
          <h4>{{album.title}}</h4>
          <p>{{album.author}}</p>
          <p>{{album.year}}</p>
      </div>

  </div>
</template>


<script>
export default {
    name:'CardContent',
    props:{
        album:Object
    }

}
</script>

<style lang="scss" scoped>
@import '@/style/variables.scss';

.ct-card{
    background-color:$secondary-color;
    padding:10px;
    display:flex;
    justify-content:center;
    flex-direction: column;
    cursor:pointer;
   box-shadow: rgba(0, 0, 0, 0.15) 0px 2px 8px;

   &:hover{
       box-shadow: rgba(0, 0, 0, 0.15) 0px 15px 25px, rgba(0, 0, 0, 0.664) 0px 5px 10px;
   }
     }

.image-container{
    width:100%;
    aspect-ratio:1;
    overflow: hidden;

    img{
        width:100%;
    }
}

.text-container{
   p{
       color:$secondary-text;
       margin-bottom:0;
       
   }

   h4{
       color:white;
       
   }
}


</style>