<template>
  <view class="coupon">
	  <cu-custom bgColor="bg-gradual-custom" :isBack="true" :isOpen="true">
	  	<block slot="backText">领取优惠券</block>
	  </cu-custom>
			<image src="../../static/images/coupon.png" class="coupon-bg"  :style="[{'top':CustomBar + 'px'}]"/>
			<image src="../../static/images/coupon-title.png"  class="coupon-title" :style="[{'top':CustomBar + 21 +'px'}]" alt="" />
			<view class="coupon-wrap">
				<view class="citem" v-for="(item,index) in detail.couponlist" :key="index">
				  <image src="../../static/images/coupon-item.png" class="citemimg" />
				  <view class="left">
					￥{{item.money}}
				  </view>
				  <view class="center">
					<view class="l">
					  {{item.ticket_name}}
					</view>
					<view class="d">
					  {{item.money_need == 0 ? '无门槛' : '满'+item.money_need+'元可用'}}
					</view>
				  </view>
				  <view class="right">
					<view :class="['unuse', item.type == 1 ? 'use' : '']">领取</view>
				  </view>
				</view>
		 
			</view>
<!-- 			<view class="coupon-input">
			  <input type="text" class="input" bindinput="bindInput"	 placeholder-style="color:#fff" placeholder="请输入手机号"/>
			  <view class="coupon-btn" @tap="getClick">一键领取</view>
			</view> -->
			<view class="coupon-info">
				<image class="coupon-info-img" src="../../static/images/coupon-info.png" />
				<view class="title">
				{{detail.info}}
				</view>
				<view class="coupon-d">
					{{detail.content}}
				</view>
			</view>
  </view>
</template>

<script>
	export default {
		data () {
			return {
				CustomBar: this.CustomBar,
				detail:{
					couponlist: [
						{
							money: '10.00',
							ticket_name: '红包标题',
							money_need: '200.00',
							type: 1
						}
					],
					info: '规则说明',
					content: '优惠券的的详细说明，文案由平台编辑好显示在这里，是可修改的。优惠券的的详细说明，文案由平台编辑好显示在这里，是可修改的。优惠券的的详细说明，文案由平台编辑好显示在这里，是可修改的。优惠券的的详细说明，文案由平台编辑好显示在这里，是可修改的。优惠券的的详细说明，文案由平台编辑好显示在这里，是可修改的。优惠券的的详细说明，文案由平台编辑好显示在这里，是可修改的。优惠券的的详细说明，文案由平台编辑好显示在这里，是可修改的。'
				}
			}
		},
		mounted() {
			console.log(this.CustomBar)
		}
	}
</script>

<style lang="scss" scoped>
	input::-webkit-input-placeholder {
		  color: white;
	}
	.coupon{
	    width:100%;
	    height:2172upx;
	    position: relative;
	    // z-index: -2;
	    .coupon-bg{
	      position: absolute;
	      top:0;
	      left:0;
	      width:100%;
	      height:2172upx;
	      z-index:-1;
	    }
	    .coupon-title{
	      width:547upx;
	      height:138upx;
	      position: absolute;
	      // top:81upx;
	      left:50%;
	      transform: translateX(-50%)
	    }
	    .coupon-des{
	      font-size: 30upx;
	      color:white;
	      position: absolute;
	      top:190upx;
	      left:50%;
	      transform: translateX(-50%)
	    }
	    .coupon-wrap{
	      position: absolute;
	      z-index: 3;
		  top:630upx;
	      left:50%;
	      transform: translateX(-50%);
	      width:594upx;
	      height: 700upx;
	      overflow-y: scroll;
	      .citem{
	        display: flex;
	        flex-direction: row;
	        // background:url('../assets/images/coupon-item.png') no-repeat;
	        // background-size: 100% 100%;
	        width:594upx;
	        height:144upx;
	        margin-bottom: 10upx;
	        position: relative;
	        .citemimg{
	          position: absolute;
	          left:0;
	          top:0;
	          width:594upx;
	          height:144upx;
	          z-index: -1;
	        }
	        .left{
	          width:210upx;
	          height:100%;
	          font-size: 48upx;
	          color:#F4472A;
	          display: flex;
	          justify-content: center;
	          align-items: center;
	        }
	        .center{
	          width:238upx;
	          height:100%;
	          display: flex;
	          flex-direction:column;
	          justify-content: center;
	          align-items: center;
	          // border-right: 1px solid rgba(255,125,104,1);
	          .l{
	            font-size: 28upx;
	            color:#F4472A;
	            font-weight: bold
	          }
	          .d{
	            font-size: 21upx;
	            color:#F4472A;
	            line-height: 35upx;
	          }
	        }
	        .right{
	          display: flex;
	          width:146upx;
	          justify-content: flex-start;
	          align-items: center;
			  .unuse{
				  width:125upx;
				  height:58upx;
				  background:linear-gradient(-30deg,rgba(255,39,39,1) 0%,rgba(255,102,51,1) 100%);
				  border-radius:29upx;
				  font-size: 27upx;
				  color:white;
				  line-height: 58upx;
				  text-align: center;
			  }
			  .use{
				  background: #CCCCCC;
			  }
	        }
	      }
	    }
	    .coupon-input{
	      position: absolute;
	      top:1342upx;
	      left:50%;
	      transform: translateX(-50%);
	      .input{
	        width:534upx;
	        height:78upx;
	        background:rgba(225,58,68,1);
	        border-radius:4upx;
	        font-size: 30upx;
	        color:#fff;
	        padding-left:15upx;
	        margin-bottom: 24upx;
	      }
	      .inputplace{
	        color:#fff !important;
	      }
	      .coupon-btn{
	        width:534upx;
	        height:85upx;
	        background:linear-gradient(0deg,rgba(255,229,126,1) 1%,rgba(255,237,164,1) 100%);
	        border-radius:4upx;
	        font-size: 34upx;
	        color:#F23C29;
	        font-weight: bold;
	        line-height: 85upx;
	        text-align: center;
	      }
	    }
	    .coupon-info{
	      width:653upx;
	      height:590upx;
	      position: absolute;
	      top:1663upx;
	      left:50%;
	      transform: translateX(-50%);
	      // background:url('../assets/images/coupon-info.png') no-repeat;
	      // background-size: 100% 100%;
	      .coupon-info-img{
	        position: absolute;
	        top:0;
	        left:0;
	        width:653upx;
	        height:590upx;
	        z-index: -1;
	      }
	      .title{
	        font-size: 34upx;
	        color:#F23C29;
	        font-weight: bold;
	        line-height: 131upx;
	        height:131upx;
	        text-align: center;
	      }
	      .coupon-d{
	        font-size: 24upx;
	        color:#491F00;
	        padding:25upx 48upx;
	        box-sizing: border-box;
	        line-height: 40upx;
	        overflow: hidden;
	        overflow-y: scroll;
	        height:400upx;
	      }
	    }
	}
</style>
