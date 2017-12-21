<template>
	<div class="slid-show">
		<a href="javascript:void(0)" >
			<div class="prev" @click="goto(prevIndex)"></div>
		</a>
		<a href="javascript:void(0)" >
			<div class="next" @click="goto(nextIndex)"></div>
		</a>
		<transition-group>
			<img v-if="isShow" :src="slides[nowIndex].src" key="item0"/>
			<p class="title" :class="{orange:nowIndex===1,orangetitle:nowIndex===1,white:nowIndex===2,whitetitle:nowIndex===2}" key="item1">{{ slides[nowIndex].title }}</p>
			<p class="text" :class="{orange:nowIndex===1,white:nowIndex===2}" key="item2">{{ slides[nowIndex].text }}</p>
		</transition-group>
		<ul>
			<li class="page-num" v-for="(item,index) in slides" @click="goto(index)" :class="{on:nowIndex===index}">{{ index+1 }}</li>
		</ul>
	</div>
</template>
<script>
	export default{
		data(){
			return {
				nowIndex: 0,
      			isShow: true,
				slides:[
					{
						src: require('../assets/1.jpg'),
						text: "步锐捷是一家领先的移动互联网技术方案提供商，针对中国智能设备市场推出移动智能终端和云端的全方位解决方案，其中包括数字标牌、电子白板、FOTA等。",
						title:""
					},
					{
						src: require('../assets/2.jpg'),
						text: "集中控制、统一管理，随时随地发布广告内容",
						title:"Aten数字标牌管理系统"
					},
					{
						src: require('../assets/3.jpg'),
						text: "强大绘图功能、云端存储课件、远程无线控制提供便捷教学体验",
						title: "电子白板软件"
					}
				]
			}
		},
		methods:{
			goto (index) {
				this.nowIndex = index
			}
		},
		computed: {
		    prevIndex () {
		      if (this.nowIndex === 0) {
		        return this.slides.length - 1
		      }else {
		        return this.nowIndex - 1
		      } 
		    },
		    nextIndex () {
		      if (this.nowIndex === this.slides.length - 1) {
		        return 0
		      }else {
		        return this.nowIndex + 1
		      }
		    }
		},
		mounted () {
			setInterval(() => {this.goto((this.nowIndex+1)%3)},5000);
		}
	}
</script>
<style>
	.slid-show,img{
		position: relative;
		width:100%;
	}
	ul{
		position: absolute;
		right: 20%;
		bottom:10px;
	}
	.page-num{
		width: 24px;
		height: 24px;
		line-height: 24px;
		border-radius: 12px;
		background: #fff;
		list-style: none;
		float:left;
		margin-left: 20px;
		text-align: center;
		cursor: pointer;
	}
	.on{
		background: #169dca;
		color: #000;
	}
	.prev,.next{
		width: 30px;
		height: 50px;
		position: absolute;
		top: 45%;
		left: 10%;
		z-index: 10;
		background-image: url('../assets/btn.png');
	}
	.next{
		left: 90%;
		background-position: 0 50px;
	}
	.text,.title{
		width: 600px;
		position:absolute;
		top: 20%;
		left: 35%;
		color: #fff;
		font-size: 24px;
		text-indent: 48px;
	}
	.title{
		top: 15%;
		left: 35%;
		text-indent: 48px;
	}
	.orange{
		top: 43%;
		left: 11%;
		color: #ff7a0f;
	}
	.orangetitle{
		top: 35%;
		font-size: 48px;
		font-weight: bold;
		color:#ff7a0f;
	}
	.white,.whitetitle{
		left: 52%;
		color: #fff;
		text-align: right;
	}
	.white{
		width: 570px;
		top: 43%;
		font-size: 26px;
	}
	.whitetitle{
		top: 35%;
		font-size: 48px;
		font-weight: bold;
	}
</style>