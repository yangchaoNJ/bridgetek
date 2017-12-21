<template>
	<div id="header">
      <a class="logo" href="#">
        <img src="../assets/logo.png" height="57" width="238" alt="">
      </a>
      <ul class="nav">
        <li v-for="(item,index) in navLists" @click="changeState(index)"><a :class="{active:change==index}" :href="item.href">{{ item.text }}</a></li>
      </ul>
    </div>
</template>
<script>
	export default{
		data () {
			return {
		        navLists:[
		          {"text":"首页","href":"#"},
		          {"text":"方案产品","href":"#"},
		          {"text":"新闻动态","href":"#"},
		          {"text":"关于我们","href":"#"},
		          {"text":"加入我们","href":"#"},
		          {"text":"联系我们","href":"#"}
		        ],
		        change: 0
		    }
		},
		methods:{
			changeState(index){
	          	this.change=index;
	        }
		}
	}
</script>
<style>
  a{
    text-decoration: none;
    text-align: center;
  }
  #header{
    width:100%;
    height: 80px;
    background: #fff;
  }
  a.logo{
    display: inline-block;
    margin-left: 370px;
    margin-top: 6px;
  }
  .logo>img{
    width:268px;
    height: 64px;
  }
  .nav{
    height: inherit;
    position: absolute;
    top: 0px;
    left: 750px;
  }
  .nav>li{
    height: 100%;
    float: left;
    list-style: none;
    margin-left: 40px;
  }
  .nav>li:hover,.nav>li>a:hover,.active{
    background: #efefef;
    color: #de8b2a !important;
  }
  .nav>li>a{
    display: inline-block;
    width:90px;
    height:100%;
    line-height: 80px;
    color: #000;
  }
</style>