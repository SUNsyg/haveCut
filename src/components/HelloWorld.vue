<template>
  <div class="hello">
    <headers></headers>
    <Swiper v-if="list.length > 0">
       <Slide v-for="(item,index) in list" :key="index">
       	<img :src="item"/>
       </Slide>
    </Swiper>
    <div class="listType">
    	<ul class="listContent">
    		<li><a><i class="iconfont icon-sanjiaoshang"></i></a><p>女装</p></li>
    		<li><a><i class="iconfont icon-sanjiaoshang"></i></a><p>女上装</p></li>
    		<li><a><i class="iconfont icon-sanjiaoshang"></i></a><p>精品</p></li>
    		<li><a><i class="iconfont icon-sanjiaoshang"></i></a><p>裙装</p></li>
    		<li><a><i class="iconfont icon-sanjiaoshang"></i></a><p>更多</p></li>
    	</ul>
    </div>
    <div class="guessYoulike">
    	<p>猜你喜欢</p>
    	<p>Guess you like</p>
    	<ul class="clothList">
    		<li v-for="(item, index) in clothList">
    			<img :src="item" />
    		</li>
    	</ul>
    </div>
  </div>
</template>

<script>
import Headers from './Header/Header'
import { Swiper, Slide } from 'vue-swiper-component';

export default {
  name: 'HelloWorld',
  data () {
    return {
      list:['../../static/img/lunbo.jpg','../../static/img/lunbo.jpg', '../../static/img/lunbo.jpg'],
      clothList:['../../static/img/cloth.jpg','../../static/img/cloth.jpg','../../static/img/cloth.jpg','../../static/img/cloth.jpg','../../static/img/cloth.jpg','../../static/img/cloth.jpg']
    }
  },
  components: {
  	Headers,
  	Swiper,
  	Slide
  }
}
</script>

<style scoped lang="scss">
.wh_slide{
	width: 100%;
	height:297px;
	img{
		width: 100%;
		height: 297px;
	}
}
.listType{
	width:100%;
	height:224px;
	border-bottom: 20px solid #f9f9f9;
	.listContent{
		display: flex;
		list-style: none;
		justify-content: space-around;
		padding-top:30px;
		li{
			width:120px;
			height:155px;
			p{
				padding-top: 13px;
				text-align: center;
				font-size: 22px/*no*/;
			} 
			a{
				display: block;
				width:120px;
				height:120px;
				background: #f9f9f9;
				border-radius: 50%;
				text-align: center;
				.iconfont{
					font-size: 70px;
				}
			}
		}
	}
}
.guessYoulike{
	width:100%;
	padding-top:20px;
	p{
		width:100%;
		text-align: center;
		&:first-child{
			font-size: 32px/*no*/;
			color:#333333;
		}
		&:nth-child(2){
			font-size: 16px/*no*/;
			color:#666666;
			padding-bottom: 10px;
		}
	}
	.clothList{
		width:100%;
		display: flex;
		flex-wrap: wrap;
		list-style: none;
		padding-right: 16px;
		li{
			width:225px;
			height:341px;
			border:1px solid #f2f2f2;
			margin-left:16px;
			margin-top:16px;
		}
	}
}
</style>
