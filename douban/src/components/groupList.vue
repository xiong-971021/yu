<template>
  <div class="list">
        <p class="title">
            <slot name="title"></slot>
        </p>
        
<img :src="url" alt="">
        <span class="name">
            <slot name="name"></slot>
        </span>
        <span class="member">
            <slot name="member"></slot>
        </span>
      
        
      <p class="topic">{{topic}}</p>
    
  </div>
</template>
<script>

export default {
  props: ["topic", "url"]
};
</script>
<style>
  .list{
    padding:0.26rem;
  }
  .list .title{
    font-size:0.5rem;
  } 
  .list img{
    width:50px;
    height:50px;
    vertical-align: middle;
  }
  .list .name{
     font-size:0.3rem;
  }
  .list .topic{
     font-size:0.3rem;
     color:#999;
  }
  .list .member{
     font-size:0.3rem;
     color:#999;
     float:right;
     margin-top:0.7rem; 
  } 
</style>