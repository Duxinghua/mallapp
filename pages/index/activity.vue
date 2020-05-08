<template>
	<view class="activity">
		<cu-custom  bgColor="bg-white-custom" :isBack="true" :isOpen="true">
			<block slot="backText">爆款优惠</block>
		</cu-custom>
		<image src="../../static/images/boombg.png" class="boombg"></image>
		<image src="../../static/images/boomtap.png" class="boomtitle"></image>
		<image src="../../static/images/boomad.png" class="boomad"></image>
		<view class="boomdes">平价超市放心购</view>
		<view class="goodlist">
			<view class="gooditem">
				<view class="goodover">
					<image mode="aspectFill" src="../../static/images/goodcover.png" class="over"></image>
					<view class="top">
						<image src="../../static/images/top1.png" class="topimg"></image>
						<text>1</text>
					</view>
				</view>
				<view class="goodinfo">
					<text class="goodsname">提子吐司5片装120g x2 软糯可口营养美味超 过两排换行软糯可口营养美味超 过两排换行糯可口营养美味超 过两排换行糯可口营养美味超 过两排换行</text>
					<text class="goodsdes">月售456</text>
					<view class="goodsprice">
						<text class="price1">￥4.8</text>
						<text class="price2">￥6.8</text>
						<view class="pricecar">
							<image src="../../static/images/carjian.png" class="jian"></image>
							<text class="carnum">1</text>
							<image src="../../static/images/carjia.png" class="jia"></image>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="carfixed">
			<image src="../../static/images/carico.png" class="carico"></image>
			<image src="../../static/images/numbg.png" class="carnum"></image>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				stroeImg:[
					'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg',
					'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg'
				]
			};
		}
	}
</script>

<style lang="scss" scoped>
page{
	background: white;
}
.activity{
	display: flex;
	flex-direction: column;
	position: relative;
	.boombg{
		position: absolute;
		left:0;
		top:0;
		width:100%;
		height:532upx;
	}
	.boomtitle{
		position: absolute;
		top:211upx;
		left:29upx;
		width:298upx;
		height:110upx;
	}
	.boomad{
		position: absolute;
		top:165upx;
		right:19upx;
		width:458upx;
		height:248upx;
	}
	.boomdes{
		position: absolute;
		top:331upx;
		left:29upx;
		font-size: 27upx;
		letter-spacing:20upx;
		color:white;
	}
	.goodlist{
		background: white;
		width:100%;
		min-height: calc(90vh - 240upx);
		position: absolute;
		top:412upx;
		left:0;
		width:100%;
		z-index: 100;
		border-radius: 21upx 21upx 0 0;
		padding:25upx 21upx;
		box-sizing: border-box;
		display: flex;
		flex-direction: column;
		.gooditem{
			display: flex;
			flex-direction: row;
			.goodover{
				width:172upx;
				height:172upx;
				border-radius: 14upx;
				position: relative;
				overflow:hidden ;
				margin-right:16upx;
				.cover{
					width:100%;
					height:100%;
				}
				.top{
					width:42upx;
					height:51upx;
					position: absolute;
					left:0;
					top:0;
					.topimg{
						width:100%;
						height:100%;
					}
					text{
						font-size: 33upx;
						color:white;
						position: absolute;
						left:50%;
						top:50%;
						transform: translate(-50%,-50%);
					}
				}
			}
			.goodinfo{
				width:calc(100% - 172upx - 16upx);
				display: flex;
				flex-direction: column;
				.goodsname{
					coloe:#333;
					font-size: 25upx;
					display: -webkit-box;
					-webkit-box-orient: vertical;
					-webkit-line-clamp: 2;
					text-overflow: ellipsis;
					overflow: hidden;
				}
				.goodsdes{
					color:#999;
					font-size: 21upx;
					line-height: 33upx;
					margin-top:10upx;
				}
				.goodsprice{
					display: flex;
					flex-direction: row;
					justify-content: space-between;
					margin-top:20upx;
					.price1{
						font-size: 25upx;
						font-weight: 800;
						color:#FF432C;
					}
					.price2{
						font-size: 25upx;
						color:#999;
						font-weight: 500;
						text-decoration: line-through;
						margin-left:10upx;
					}
					.pricecar{
						min-width:142upx;
						margin-left:auto;
						display: flex;
						flex-direction: row;
						.jian,.jia{
							width:42upx;
							height:42upx;
						}
						.carnum{
							min-width: 58upx;
							font-size: 33upx;
							text-align: center;
							coloe:#333;
						}
					}
				}
			}
		}
	}
	.carfixed{
		position: fixed;
		right:21upx;
		bottom: 150upx;
		width:125upx;
		height:125upx;
		z-index: 400;
		.carico{
			position: absolute;
			width:100%;
			height:100%;
			left:0;
			top:0;
		}
		.carnum{
			position: absolute;
			right:0;
			top:0;
			width:50upx;
			height:50upx;
		}
	}
}
</style>
