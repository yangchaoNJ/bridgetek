<template>
	<div>
		<div class="top">
			<h2>移动互联网和云端解决方案</h2>
			<p>公司自成立以来，完成多个移动互联网和云端相关的项目，积累了丰富的行业经验</p>
			<span>公司的移动互联网解决方案包括</span>
		</div>
		<div class="main">
			<div class="items" v-for="(item,index) in items" @mouseleave="turn(index)">
				<div class="containImg">
					<img :src="item.url" alt="">
					<p class="titles">{{ item.title }}</p>
				</div>
				<div class="rotate">
					<h2>{{ item.title }}</h2>
					<p class="content">{{ item.content }}</p>
					<a class="btn" :href="item.path">查看详情</a>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
	export default{
		data(){
			return {
				items:[
					{
						title:"电子白板",
						content:"借助强大的编辑以及云存储功能，客户可以畅怀书写并且可以随时随地编辑内容、存储到云端甚至提前发送至白板终端。",
						url:require("../assets/whiteboard.jpg"),
						path:"https://www.baidu.com"
					},
					{
						title:"数字标牌",
						content:"借助优秀的Aten数字标牌内容发布、设备管理系统，客户可以轻松的管理广告机、数字班牌甚至任何智能移动终端。",
						url:require("../assets/digitalsin.jpg"),
						path:"https://www.baidu.com"
					},
					{
						title:"空中升级",
						content:"步锐捷为客户提供先进的空中固件升级方案（FOTA）。从共有云到私有云，任何Android设备均能轻松接入我们的服务。",
						url:require("../assets/airupgrade.jpg"),
						path:"https://www.baidu.com"
					},
					{
						title:"车联网",
						content:"借助资深的智能移动操作系统经验，我们为客户提供从操作系统到上层业务实现的完整解决方案。",
						url:require("../assets/carnetworking.jpg"),
						path:"https://www.baidu.com"
					}
				]
			}
		},
		methods:{
			turn(index){
				
			}
		}
	}
</script>
<style>
	.top,.main{
		width:1200px;
		margin: 0 auto;
	}
	.top>h2,.top>p{
		width: 100%;
		text-align: center;
	}
	h2{
		font-size: 24px;
		font-weight: normal;
    	color: #505050;
    	margin-top: 30px;
	}
	.top>p{
		font-size: 16px;
    	color: #505050;
    	margin-top: 18px;
	}
	.top>span{
		width: 252px;
		font-size: 18px;
	    color: #df9329;
	    display: block;
	    padding: 4px 0;
	    border: 1px solid #DF9329;
	    border-right: none;
	    border-left: none;
	    margin: 18px auto;
	}
	.items{
		float: left;
		margin: 27px;
		position: relative;
	}
	.items>*{
		backface-visibility: hidden;
		transform-style: preserve-3d;
		transition: transform .5s ease-in-out;
	}
	.containImg,.items img{
		border-radius: 10px;
	}
	.titles{
		width:186px;
		height:48px;
		position: absolute;
		top:40%;
		left:32%;
		border:1px solid #fff;
		color: #fff;
		font-size: 32px;
		text-align: center;
		cursor:default;
	}
	.items:hover .rotate{
		z-index: 1;
		transform-style: preserve-3d;
		transform: rotateY(0deg);
	}
	.rotate{
		transform: rotateY(180deg);
		width:100%;
		height:100%;
		position: absolute;
		top: 0px;
		background: #fff;
		border: 1px solid #ccc;
		border-radius: 10px;
	}
	.rotate>h2{
		text-align: center;
		margin-top: 10px;
	}
	.rotate>*{
		cursor: default;
	}
	.content{
		width:80%;
		margin: 0 auto;
		margin-top: 20px;
		font-size: 14px;
	    color: #9b9b9b;
	    line-height: 24px;
	}
	.btn{
		width:140px;
		height: 45px;
		display: block;
		background: #DE8B2A;
		color: #fff;
		text-align: center;
		line-height: 45px;
		border-radius: 3px;
		margin: 40px auto;
		cursor: pointer;
	}
</style>