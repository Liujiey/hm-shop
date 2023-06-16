<template>
	<view class="member">
		<view class="box1">
			<image src="../../static/logo.jpg"></image>
			<view class="info">
				<view>阿吧阿吧</view>
				<view>用户名：jufeitu14138155</view>
				<button style="font-size: 1px; width: 70px; height: 20px; background-color: #fff;  "></button>
				<view><text class="iconfont icon-jiahao"></text><text>状态</text></view>
			</view>
			<view class=" icon iconfont icon-erweima">
				
			</view>
			<text class="jiantou">></text>
		</view>
		<view class="kong"></view>
		<view class="box2">
			<view class="iconfont icon-juminfuwuxiuliheqitafuwuye" style="color: green;"></view>
			<text>服务</text>
			<text>></text>
		</view>
		<view class="kong"></view>
		<view class="box2">
			<view class="iconfont icon-shoucang" style="color: green;"></view>
			<text>收藏</text>
			<text>></text>
		</view>
		<view class="box3">
			<view class="iconfont icon-pengyouquan" style="color: green;"></view>
			<text>服务</text>
			<text>></text>
		</view>
		<view class="box3">
			<view class="iconfont icon-qiabao" style="color: green;"></view>
			<text>服务</text>
			<text>></text>
		</view>
		<view class="box3">
			<view class="iconfont icon-fabiaoqing" style="color: green;"></view>
			<text>服务</text>
			<text>></text>
		</view>
		<view class="kong"></view>
		<view class="box3">
			<view class="iconfont icon-shezhi" style="color: green;"></view>
			<text>服务</text>
			<text>></text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	.member{
		width: 100%;
		height: 750px;
		background-color: #eee;
	}
	.box1{
		padding: 30rpx;
		display: flex;
		background-color: #fff;
		image{
			border-radius: 10px;
			width: 130rpx;
			height: 130rpx;
		}
		.info{
			margin-left: 40rpx;
			line-height: 60rpx;
			view:nth-child(1){
				font-size: 40rpx;
			}
			view:nth-child(2){
				font-size: 28rpx;
				color: #333;
				opacity: 0.8;
			}
			view:nth-child(3){
				width: 100rpx;
				font-size: 28rpx;
				border: 1px solid #eee;
				text-align: center;
				border-radius: 30px;
				color: #333;
				opacity: 0.8;
			}
		}
		.icon{
			margin-left: 45rpx;
			margin-top: 70rpx;
		}
		.jiantou{
			margin-left: 30rpx;
			margin-top: 70rpx;
			color: #999;
		}
	}
	.box2{
		display: flex;
		padding: 20rpx;
		background-color: #fff;
		view{
			margin-top: 8rpx;
		}
		text:nth-child(2){
			font-size: 32rpx;
			margin-left: 30rpx;
		}
		text:nth-child(3){
			font-size: 32rpx;
			margin-left: 280px;
			color: #999;
			margin-top: 1rpx;
		}
	}
	.box3{
		background-color: #fff;
		display: flex;
		padding: 20rpx;
		view{
			margin-top: 8rpx;
		}
		text:nth-child(2){
			font-size: 32rpx;
			margin-left: 30rpx;
		}
		text:nth-child(3){
			font-size: 32rpx;
			margin-left: 280px;
			color: #999;
			margin-top: 1rpx;
		}
	}
	.kong{
		width: 100%;
		height: 20rpx;
		background-color: #eee;
		border-radius: 3px;
	}
</style>
