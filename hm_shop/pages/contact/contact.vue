<template>
	<view class="contact">
		<image class="img" src="http://www.itcast.cn/2018czydz/images/gywmban.jpg" mode=""></image>
		<view class="info">
			<view @click="phone()">联系电话：400-618-9090（ 点击拨打 ）</view>
			<view>校区地址：江苏省无锡市惠山区钱藕路1号江苏信息职业技术学院</view>
		</view>
		<map class="map" :longitude="longitude" :latitude="latitude" :markers="markers"></map>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				longitude:120.1684548094482,
				latitude:31.569563906985543,
				scale:15,
				markers:[
					{
						longitude:120.1684548094482,
						latitude:31.569563906985543,
						iconPath:'../../static/logo.jpg',
						width:30,
						height:30,
						
					}
					
				]
			}
		},
		methods: {
			phone(){
				uni.makePhoneCall({
					phoneNumber:'400-618-9090'
				})
			}
		}
	}
</script>

<style lang="scss">
	.contact{
		.img{
			width: 750rpx;
			height: 320rpx;
		}
		.info{
			padding: 10rpx 20rpx;
			font-size: 30rpx;
			view{
				line-height: 80rpx;
				border-bottom: 1px solid #eee;
			}
		}
		map{
			width: 750rpx;
			height: 750rpx;
		}
	}
</style>
