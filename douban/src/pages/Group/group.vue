<template>
    <div>
         <Myheader txt="小组">
            <img :src="searchUrl" alt="" slot="left" class="leftImg">
            <img :src="chatUrl" alt="" slot="right" class="rightImg"> 
        </Myheader>

        <!-- 数据列表 -->
        <List v-for="(item,i) in arr" :key="i" :topic="item.group_list[i].topic_title" :url="item.group_list[i].img_url">
            <span slot="title">{{item.title}}</span>
            <span slot="name">{{item.group_list[i].group_name}}</span>
            <span slot="member">{{item.group_list[i].group_member}}</span>
        </List>
<!--  -->
    </div>
</template>
<script>
import search from './img/ic_actionbar_search_icon.png'
import chat from './img/ic_chat_green.png'

import Myheader from '@/components/header'
import List from '@/components/groupList'

import axios from "axios"
export default {
    data(){
        return{
            chatUrl:chat,
            searchUrl:search,
            arr:[]
        }
    },
    components:{
        Myheader,
        List
    },
      mounted() {
    axios
      .get("../../../static/data/groupData.json")
      .then(res => {
        console.log(res);
        this.arr = res.data.group;
      })
      .catch(err => {
        console.log(err);
      });
  }
    
}
</script>