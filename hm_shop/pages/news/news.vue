<template>
	<view class="news">
		<news-item @itemClick="goDetail" :newsList="newsList"></news-item>
	</view>
</template>

<script>
	import newsItem from '../../components/news-item/news-item.vue'
	export default {
		data() {
			return {
				newsList:[]
			}
		},
		methods: {
			async getNews (){
				const res = await this.$myRuquest({
					url:'/api/getnewslist'
				})
				this.newsList = res.data.message
				console.log(this.newsList)
			},
			goDetail(id){
				console.log(id)
				uni.navigateTo({
					url:'/pages/news-detail/news-detail?id='+id
					
				})
			}
		},
		components:{
			"news-item":newsItem
		},
		onLoad(){
			this.getNews()
		}
	}
</script>

<style lang="scss">
	
</style>
