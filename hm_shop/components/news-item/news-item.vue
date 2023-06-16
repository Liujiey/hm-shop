<template>
	<view>
		<view class="news_item" @click="navigator(item.id)" v-for="item in newsList" :key="item.id">
			<image :src="item.img_url"></image>
			<view class="right">
				<view class="tit">
					{{item.title}}
				</view>
				<view class="info">
					<!-- vue中试用过滤器的语法，会读取 | 左边的值传入到右边定义的过滤器，然后过滤器中返回 -->
					<text>发表时间：{{item.add_time | formatDate}}</text>
					<text>浏览:{{item.click}}</text>
				</view>
			</view>
		</view>
	</view>
	
</template>

<script>
	
	export default {
		name:"news-item",
		data() {
			return {
				
			};
		},
		props:['newsList'],
		filters:{
			formatDate(date){
				const nDate = new Date(date)
				const year = nDate.getFullYear()
				const month = nDate.getMonth().toString().padStart(2,0)
				const day = nDate.getDay().toString().padStart(2,0)
				return year+'-'+month+'-'+day
			}
		},
		methods:{
			navigator(id){
				this.$emit('itemClick',id)
			}
		}
	}
</script>

<style lang="scss">
	.news{
		.news_item{
			display: flex;
			padding: 10rpx 20rpx;
			border-bottom: 1px solid $shop_color;
			image{
				width: 200rpx;
				min-width: 200rpx;
				max-width: 200rpx;
				height: 150rpx;
			}
			.right{
				margin-left: 15rpx;
				display: flex;
				flex-direction: column;
				justify-content: space-between;
				.tit{
					font-size: 33rpx;
					
				}
				.info{
					font-size: 24rpx;
					text:nth-child(2){
						margin-left: 30rpx;
					}
				}
			}
			
		}
	}
</style>