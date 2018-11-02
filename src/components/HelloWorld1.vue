<template>
<div class="index">
    <div class="search">
      <el-input prefix-icon="el-icon-search" placeholder="请输入" size="small"></el-input>
      </div>
 <div class="index_logo">
  <h1>logo</h1>
   </div>
   <div class="navmenu">
     <el-menu :defaultIndex="activeIndex"
      class="el-munu" 
      mode="horizontal"
       @select="handleSelect" 
       background-color="#409EFF"
       text-color="#fff">
       <el-menu-item index="1">首页</el-menu-item>
       <el-submenu index="2" >
         <template slot="title">关于众基</template>
         <el-menu-item index="2-1">公司简介</el-menu-item>
         <el-menu-item index="2-2">荣誉展示</el-menu-item>
         <el-menu-item index="2-3">企业动态</el-menu-item>
         <el-menu-item index="2-4">企业文化</el-menu-item>
       </el-submenu>
       <el-submenu index="3">
         <template slot="title">业务领域</template>
         <el-menu-item index="3-1">智慧城市</el-menu-item>
         <el-menu-item index="3-2">智慧林业</el-menu-item>
         <el-menu-item index="3-3">安防系统</el-menu-item>
         <el-menu-item index="3-4">无线通讯</el-menu-item>
         <el-menu-item index="3-5">更多业务</el-menu-item>
         </el-submenu>
         <el-menu-item index="4">经典案例</el-menu-item>
         <el-menu-item index="5">合作伙伴</el-menu-item>  
     </el-menu>
   </div>
<div>
  <el-carousel :interval="5000" arrow="always">
    <el-carousel-item v-for="item in pic" :key="item.id">
     <h3><img :src="item.src"></h3>
    </el-carousel-item>
  </el-carousel>
  </div>
  <div class="zjAdvantage">
    <h2>我们的优势</h2>
  <ul>
   <li><div class="card"><img src="/static/img/home_card01.png"><h3>优质的服务</h3></div></li>
   <li><div class="card"><img src="/static/img/home_card02.png"><h3>丰富的经验</h3></div></li>
   <li><div class="card"><img src="/static/img/home_card03.png"><h3>完美的售后</h3></div></li>
  </ul>
  </div>
  <div class="zjAdvantage">
    <h2>应用领域</h2>
   <ul>
   <li><div class="card1"><img src="/static/img/home_card01.png"><h3>智慧林业</h3></div></li>
   <li><div class="card1"><img src="/static/img/home_card02.png"><h3>智慧城市</h3></div></li>
   <li><div class="card1"><img src="/static/img/home_card03.png"><h3>安防系统</h3></div></li>
   <li><div class="card1"><img src="/static/img/home_card03.png"><h3>无线通讯</h3></div></li>
  </ul>
    </div>
  </div>
</template>

<style>
.index {
  width: 90%;
  margin: 0px auto;
  text-align: center;
}

.search{
  float:right;
}
.el-carousel__item h3 {
  color: #475669;
  font-size: 18px;
  opacity: 0.75;
  line-height: 300px;
  margin: 0;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}
.el-menu--horizontal > .el-menu-item {
  width: 200px;
}
.el-menu--horizontal > .el-submenu .el-submenu__title {
  width: 200px;
}
.zjAdvantage{
text-align:center;
margin-top:20px;
}
.zjAdvantage h2{
  color:#409EFF;
  width:300px;
  border-bottom:2px solid #409EFF;
  margin:0px auto;
}
.zjAdvantage h4{
  width:100px;
  height:100px;
  transition:width 2s,height 2s;
  background-color:#99a9bf;
}
.zjAdvantage h4:hover{
  width:150px;
  height:150px;
   background-color:#99a9bf;
}
.zjAdvantage ul{
  width:980px;
  margin:0px auto;
}
.zjAdvantage li{
  list-style:none;
   box-sizing: border-box;
  float:left;
  margin:60px;
   height:170px;
   opacity:.7;

}
.zjAdvantage li:hover{
  list-style:none;
   box-sizing: border-box;
  float:left;
  margin:60px;
  opacity:1;
}
.zjAdvantage img{
width:160px;
height:120px;
 background-color:#409EFF;
}
.card1 img{
  width:120px;
  height:120px;
  border-radius:50% 50%;
}
</style>
<script>
import MyTest from './test'
import myHeader from './header'
export default {
  data() {
    return {
       valueChild:true,
       posts:{},
      activeIndex: "1",
      pic: [
        { id: "1", src: "/static/img/coat.jpg" },
        { id: "2", src: "/static/img/corn.jpg" },
        { id: "3", src: "/static/img/T.jpg" },
        { id: "4", src: "/static/img/mung.jpg" }
      ]
    };
  },
  methods: {
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    },
     changeValue(){
            this.valueChild = !this.valueChild
        }
  },
  components:{
  MyTest,
  myHeader
  }
};
</script>