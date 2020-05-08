<template>
	<view class="content">
		<cu-custom bgColor="bg-gradual-custom" :isBack="true">
			<block slot="backText">首页</block>
		</cu-custom>
		<view class="page-top">
			<view class="bg">
				<view class="search-wrap">
					<icon type="search" size="18"/>
					<text class="searchText">请输入关键字</text>
				</view>
				<swiper class="screen-swiper screen-swiper-fix" :class="'square-dot'" :indicator-dots="true" :circular="true"
				 :autoplay="true" interval="5000" duration="500">
					<swiper-item v-for="(item,index) in swiperList" :key="index" class="itemimg">
						<image :src="item.url" mode="aspectFill" v-if="item.type=='image'" class="itemimg"></image>
					</swiper-item>
				</swiper>
			</view>
			<view class="menu-wrap">
				<view class="menuItem" v-for="(item,index) in cateList" :key="index">
					<image mode="aspectFill" :src="item.url" class="menuimg"></image>
					<text class="cateName">{{item.cate_name}}</text>
				</view>
			</view>
		</view>
		<image src="../../static/images/coupon-ads.png" class="page-ad" @click="couponClick"/>
		<view class="page-hot">
			<view class="hot-title">
				<text class="hot1">优惠爆款</text>
				<text class="hot2">放心购</text>
				<view class="hot-go">
					<text>去逛逛</text>
					<image src="../../static/images/arrow.png" class="arrowico"></image>
				</view>
			</view>
			<view class="hot-content">
				<GoodsItem :width="179" :obj="item" :key="index" @goodsClick="goodsClick" @carClick="carClick" v-for="(item,index) in objList"></GoodsItem>
			</view>
		</view>
		<view class="page-menu">
			<view class="menuwrap">
				<view :class="['menuItem',navIndex == index ? 'active' : '']" v-for="(item,index) in goodsCate" :key="index" @click="navClick(index)">
					<text class="title1">{{item.cate_name}}</text>
					<text :class="['title2',navIndex == index ? 'active' : '']">{{item.cate_des}}</text>
				</view>
			</view>
		</view>
		<view class="page-goodslist">
			<view class="goodlist">
				<GoodsItem :width="347" :obj="item" :key="index" @goodsClick="goodsClick" @carClick="carClick" v-for="(item,index) in objList"></GoodsItem>
			</view>
		</view>
	</view>
</template>

<script>
	import GoodsItem from '../../components/goodsitem.vue'
	export default {
		data() {
			return {
				navIndex:0,
				swiperList: [
					{
						id: 0,
						type: 'image',
						url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg'
					}, {
						id: 1,
						type: 'image',
						url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big37006.jpg',
					}, {
						id: 2,
						type: 'image',
						url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big39000.jpg'
					}, {
						id: 3,
						type: 'image',
						url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big10001.jpg'
					}, {
						id: 4,
						type: 'image',
						url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big25011.jpg'
					}, {
						id: 5,
						type: 'image',
						url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big21016.jpg'
					}, {
						id: 6,
						type: 'image',
						url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big99008.jpg'
					},
				],
				cateList: [
					{
						id:1,
						url:'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg',
						cate_name:'蔬菜豆制品'
					},
					{
						id:1,
						url:'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg',
						cate_name:'蔬菜豆制品'
					},
					{
						id:1,
						url:'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg',
						cate_name:'蔬菜豆制品'
					},
					{
						id:1,
						url:'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg',
						cate_name:'蔬菜豆制品'
					},
					{
						id:1,
						url:'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg',
						cate_name:'蔬菜豆制品'
					},
					{
						id:1,
						url:'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg',
						cate_name:'蔬菜豆制品'
					},
					{
						id:1,
						url:'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg',
						cate_name:'蔬菜豆制品'
					},
					{
						id:1,
						url:'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg',
						cate_name:'蔬菜豆制品'
					},
					{
						id:1,
						url:'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg',
						cate_name:'蔬菜豆制品'
					}
				],
				objList: [
					{
						goods_id:1,
						goods_name: '测试测试测试测试测试测试',
						price:'10.00',
						oldprice:'111.00',
						image:require('../../static/images/goodcover.png'),
						num:1
					},
					{
						goods_id:1,
						goods_name: '测试测试',
						price:'10.00',
						oldprice:'1.00',
						image:require('../../static/images/goodcover.png'),
						num:1
					},
					{
						goods_id:1,
						goods_name: '测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试',
						price:'10.00',
						oldprice:'1.00',
						image:require('../../static/images/goodcover.png'),
						num:1
					},
					{
						goods_id:1,
						goods_name: '测试测试测试测试测试测试测试测试',
						price:'10.00',
						oldprice:'1.00',
						image:require('../../static/images/goodcover.png'),
						num:1
					},
					{
						goods_id:1,
						goods_name: '测试测试',
						price:'10.00',
						oldprice:'1.00',
						image:require('../../static/images/goodcover.png'),
						num:1
					},
					{
						goods_id:1,
						goods_name: '测试测试',
						price:'10.00',
						oldprice:'1.00',
						image:require('../../static/images/goodcover.png'),
						num:1
					},
					{
						goods_id:1,
						goods_name: '测试测试',
						price:'10.00',
						oldprice:'1.00',
						image:require('../../static/images/goodcover.png'),
						num:1
					}
				],
				goodsCate:[
					{
						id:-1,
						cate_name: '全部',
						cate_des:'海量商品'
					},
					{
						id:1,
						cate_name:'推荐',
						cate_des: '最懂你'
					},
					{
						id:2,
						cate_name: '便宜好贷',
						cate_des: '低价抢购'
					},
					{
						id:3,
						cate_name: '生活用品',
						cate_des: '应有尽有'
					}
				]
				
			}
		},
		onLoad() {

		},
		methods: {
			goodsClick(e){
				console.log(e)
			},
			carClick(e){
				console.log(e)
			},
			navClick(index) {
				this.navIndex = index
			},
			couponClick(e) {
				console.log(1)
				uni.navigateTo({
                    url: '/pages/index/coupon',
                    success: res => {},
                    fail: () => {
						console.log(111)
					},
                    complete: () => {}
                })
			}
		},
		components:{
			GoodsItem
		}
	}
</script>

<style lang="scss" coped>
	page{
		background: #f8f8f8;
	}
	.content {
		display: flex;
		flex-direction: column;
		width:100%;
		min-height: 100vh;
	}
	.page-top{
		display: flex;
		flex-direction: column;
		background-color: white;
	}
	.page-ad{
		width:100%;
		height:206upx;
		margin:15upx auto 0upx auto;
	}
	.bg{
		height: 280upx;
		width:100%;
		background-image: linear-gradient(120deg, #ff6634, #ff362a);
		padding:30upx;
		box-sizing: border-box;
		.search-wrap{
			width:100%;
			height:62upx;
			border-radius: 30upx;
			overflow: hidden;
			background: white;
			margin-bottom: 30upx;
			padding:30upx;
			box-sizing: border-box;
			display: flex;
			align-items: center;
			.searchText{
				padding-left:30upx;
				color:#666;
			}
		}
	}
	.screen-swiper-fix{
		height:340upx;
		border-radius: 30upx;
		overflow: hidden;
	}
	.itemimg{
		border-radius: 30upx;
		overflow: hidden;
	}
	.menu-wrap{
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		padding:0 30upx;
		margin-top:240upx;
		box-sizing: border-box;
		.menuItem{
			width:20%;
			display: flex;
			flex-direction: column;
			align-items: center;
			margin-bottom:30upx;
			.menuimg{
				width:104upx;
				height: 104upx;
				border-radius: 50%;
				overflow: hidden;
			}
			.cateName{
				margin-top:15upx;
				font-size: 22upx;
				color:#333;
			}
		}
	}
	.page-hot{
		width:690upx;
		display: flex;
		flex-direction: column;
		height:408upx;
		padding:15upx;
		box-sizing: border-box;
		background:linear-gradient(-30deg,rgba(255,39,39,1) 0%,rgba(255,102,51,1) 100%);
		border-radius:14px;
		margin: 0 auto;
		.hot-title{
			display: flex;
			flex-direction: row;
			justify-content: flex-start;
			align-items: flex-end;
			margin-bottom: 20upx;
			margin-top:10upx;
			.hot1{
				font-size: 35upx;
				color:#fff;
				font-weight:800;
			}
			.hot2{
				font-size: 23upx;
				color:#fff;
				font-weight:800;
				margin-left:30upx;
				padding-left: 30upx;
				position: relative;
			}
			.hot2::after{
				position: absolute;
				content:"";
				left:0;
				top:50%;
				transform: translateY(-50%);
				width:2upx;
				height:70%;
				background-color: white;
			}
			.hot-go{
				display: flex;
				flex-direction: row;
				align-items: center;
				margin-left:auto;
				padding:10upx 16upx;
				background:white;
				border-radius: 20upx;
				text{
					font-size: 21upx;
				}
				image{
					width:8upx;
					height:15upx;
				}
			}
		}
		.hot-content{
			width:100%;
			height:303upx;
			background:rgba(255,255,255,1);
			border-radius:7upx;
			overflow: hidden;
			overflow-x: scroll;
			padding-top:14upx;
			padding-right:14upx;
			padding-left:14upx;
			box-sizing: border-box;
			display: flex;
			flex-direction: row;
		}
	}
	.page-menu{
		position: static;
		display: flex;
		padding-left:21upx;
		padding-right:21upx;
	    box-sizing: border-box;
		.menuwrap{
			// position: absolute;
			display: -webkit-box; 
			overflow: hidden;
			overflow-x: auto;
			width: 100%;
			margin-top:20upx;
			.menuItem{
				display: flex;
				flex-direction: column;
				align-items: center;
				width:150upx;
				margin-right:60upx;
				.title1{
					font-size: 35upx;
					font-weight: 800;
					color:#333;
				}
				.title2{
					font-size: 23upx;
					color:#666;
					font-weight: 500;
					margin-top:10upx;
				}
				.active{
					padding:8upx 15upx;
					background:#FF6633;
					border-radius: 18upx;
					color:white;
				}
			}
			.active{
				.title1{
					color:#FF432C
				}
			}
		}

	}
	.page-goodslist{
		display: flex;
		flex-direction: column;
		padding:21upx;
		box-sizing: border-box;
		margin-top:10upx;
		.goodlist{
			-moz-column-count:2;
				/* Firefox */
			-webkit-column-count:2;
				/* Safari 和 Chrome */
			column-count:2;
			-moz-column-gap:14upx;
			-webkit-column-gap:14upx;
			column-gap:14upx;
			height:100%;
			overflow: auto;
		}
	}
</style>
