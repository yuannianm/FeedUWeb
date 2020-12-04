<template>
  <div>
    <H1>Home</H1>
    <input v-model="url" placeholder="input your rss source" >
    <router-link :to="link+encodeURIComponent(url)" replace>Go</router-link>
    <input v-model="bilibiliuid" placeholder="input your bilibili uid" >
    <router-link :to="bilibililink+bilibiliuid" replace>Go</router-link>
    <input v-model="weibouid" placeholder="input your weibo uid" >
    <router-link :to="weibolink+weibouid" replace>Go</router-link>
    <router-view :key="$route.fullPath" />
  </div>
</template>
<script>
export default {
  data(){
    let bilibiliuid,weibouid
    let url=''
    let link="/rss/others/"
    let bilibililink="/rss/bilibili/"
    let weibolink="/rss/weibo/"
    return {
      bilibiliuid,
      weibouid,
      url,
      link,
      bilibililink,
      weibolink
    }
  },
};

</script>
<style scoped>
div
{
border:2px groove;
border-radius:10px;
box-shadow: 10px 10px 5px #888888;
}
</style>