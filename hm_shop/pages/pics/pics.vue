<template>
	<view class="pics">
		<scroll-view class="left" scroll-y="true">
			<view @click="leftClickHandle(index,item.id)" :class="active===index? 'active' : ''" v-for="(item,index) in cates" :key="item.id">{{item.title}}</view>
			
		</scroll-view>
		<scroll-view class="right" scroll-y="true">
			<view class="item" v-for="item in secondData" :key="item.id">
				<image @click="previewImg(item.img_url)" :src="item.img_url"></image>
				<text>{{item.title}}</text>
			</view>
			<text v-if="secondData.length === 0">暂无数据</text>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				cates:[],
				active:0,
				secondData:[],
				urls:[]
			}
		},
		methods: {
			async getPicsCate(){
				const res = await this.$myRuquest({
					url:'/api/getimgcategory'
				})
				this.cates = res.data.message
				console.log(this.cates)
				this.leftClickHandle(0,this.cates[0].id)
			},
			async leftClickHandle(index,id){
				this.active=index
				const res = await this.$myRuquest({
					url:'/api/getimages/'+id
				})
				this.secondData = res.data.message
				console.log(this.secondData)
			},
			previewImg(current){
				const urls = this.secondData.map(item=>{
					return item.img_url
				})
				console.log(urls)
				uni.previewImage({
					urls,
					current
				})
			}
			
		},
		onLoad(){
			this.getPicsCate()
		}
	}
</script>

<style lang="scss">
	page{
		height: 100%;
	}
	.pics{
		height: 100%;
		display: flex;
		.left{
			width: 200rpx;
			height: 100%;
			border-right: 1px solid #eee;
		}
		view{
			height: 60px;
			line-height: 60px;
			color: #333;
			text-align: center;
			font-size: 30rpx;
			border-top: 1px solid #eee;
		}
		.active{
			background-color: $shop-color;
			color: #fff;
		}
		.right{
			height: 100%;
			width: 520rpx;
			margin: 10rpx auto;
			.item{
				height: 60%;
				box-sizing: border-box;
				image{
					width: 520rpx;
					height: 520rpx;
					border-radius: 5px;
				}
				text{
					font-size: 30rpx;
					top: 540rpx;
				}
			}
			}
		
	}
</style>
