<template>
	<view class="detail">
		<cu-custom bgColor="bg-gradual-custom" :isBack="true" :isOpen="true">
			<block slot="backText">商品详情</block>
		</cu-custom>
		<view class="swiperwrap">
			<swiper class="store-swiper" :indicator-dots="false" :autoplay="true" :interval="3000"
			  @change="storeChange">
					<swiper-item v-for="(item,index) in stroeImg" :key="index">
						<image :src="item" mode="scaleToFill"  class="swiperimg"/>
					</swiper-item>
			</swiper>
			<view class="top">
				<view class="gosearch">
					<image src="../../static/images/gosearch.png" class="gosearchico"></image>
					<text>请输入关键词</text>
				</view>
				<image src="../../static/images/gocar.png" class="gocar"></image>
				<image src="../../static/images/goshare.png" class="gocar"></image>
			</view>
			<view class="fix">{{currentIndex}}/{{stroeImg.length}}</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				stroeImg:[
					'http://t8.baidu.com/it/u=3571592872,3353494284&fm=79&app=86&f=JPEG?w=1200&h=1290',
					'http://t8.baidu.com/it/u=3571592872,3353494284&fm=79&app=86&f=JPEG?w=1200&h=1290'
				],
				currentIndex:1
			};
		},
		methods:{
			storeChange(e){
				this.currentIndex = e.detail.current + 1
			}
		}
	}
</script>

<style lang="scss" scoped>
	.detail {
		width: 100%;
		display: flex;
		flex-direction: column;
		.swiperwrap {
			width: 100%;
			height: 750upx;
			position: relative;
			.store-swiper{
				height:750upx!important;
				.swiperimg{
					width:100%;
					height:100%;
				}
				
			}
			.top{
				position: absolute;
				left:50%;
				transform: translateX(-50%);
				top:50upx;
				display: flex;
				flex-direction: row;
				width:100%;
				padding-left:38upx;
				padding-right:38upx;
				box-sizing: border-box;
				.gosearch{
					width:calc(100% - 126upx - 74upx);
					margin-right:auto;
					height:63upx;
					background:rgba(0,0,0,1);
					opacity:0.6;
					border-radius:31upx;
					display: flex;
					justify-content: flex-start;
					padding-left:24upx;
					padding-right:24upx;
					box-sizing: border-box;
					align-items: center;
					.gosearchico{
						width:28upx;
						height:28upx;
						margin-right:24upx;
					}
					text{
						font-size: 24upx;
						color:#ccc;
					}
					
				}
				.gocar{
					width:63upx;
					height:63upx;
				}
				.gocar:nth-last-child(2){
					margin-right:37upx;
				}
			}
			.fix{
				position: absolute;
				bottom: 40upx;
				left:50%;
				transform: translateX(-50%);
				width:67upx;
				height:42upx;
				background:rgba(51,51,51,1);
				opacity:0.6;
				border-radius:21upx;
				color: white;
				font-size: 25upx;
				line-height: 42upx;
				text-align: center;
			}
		}
	}
</style>
