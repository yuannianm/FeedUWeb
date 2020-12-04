<template>
<div>
<h1>Rss</h1>
    <ul>
    <li  v-for="item in items" :key="item.pubDate" >
     标题:<br>{{item.title}}<br>
      描述:<div v-if="item.description" v-html="item.description.value"> {{item.description.value}}</div><br>
      链接:{{item.link}}<br>
      图片:<br><img width="400px" referrerpolicy="no-referrer" v-for="pic in item.enclosures" :src=pic.url :key="pic.url">
      <!--  -->
      <br>时间:{{item.pubDate}}<br>作者:{{item.author}} 
      <hr>
    </li>
    </ul>
</div>
</template>
<script>

export default {
    data(){
    let items='null';
    let reqUrl='http://localhost:8080/rss/';
    if (this.$route.params.type=="bilibili") {
      reqUrl="http://localhost:8080/rss/bilibili?uid="
      this.get(reqUrl+this.$route.params.uid).then(resp=>{
      this.items=resp.items
      }).catch((resp)=>{
      console.log(resp)
    });
    } else if(this.$route.params.type=="weibo") {
      reqUrl="http://localhost:8080/rss/weibo?uid="
      this.get(reqUrl+this.$route.params.uid).then(resp=>{
      this.items=resp.items
      }).catch((resp)=>{
      console.log(resp)
    });
    } else if(this.$route.params.type=="others"){
      reqUrl="http://localhost:8080/rss/proxy?url="
      this.get(reqUrl+decodeURIComponent(this.$route.params.uid)).then(resp=>{
      this.items=this.$x2js.xml2js(resp).rss.channel.item
      }).catch((resp)=>{
      console.log(resp)
    });
    }
    return{
      items
    }
  },
}
</script>
<style  scoped>
div{
  background-color: gray ;
}
hr{
  background-color:white;
  height: 3px;
}
</style>