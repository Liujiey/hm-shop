<template>
	<view>
		<view class="box1">
			<view class="shop">
				<view class="dian">
					<a :class="name"  href="" @click.prevent="Function($event)"></a>
				</view>
				<view class="iconfont icon-shangpu" style="font-size: 30px; margin-top: -10rpx; margin-left: 20rpx; "></view>
				<text class="content">苹果自营店</text>
				<view class="iconfont icon-jinrujiantou" style=" font-size: 32px; margin-top: -10rpx;"></view>
			</view>
			<view class="good">
				<view class="dian">
					<a :class="name"  href="" @click.prevent="Function($event)"></a>
				</view>
				<image class="img" style="width: 300rpx; height: 300rpx; margin-top: -30px; " src="../../static/thumb_201504200119256520.jpg" mode=""></image>
				<view class="">
					<text>Apple iMac MF883CH/A 21.5英寸一体机电脑</text>
					<view class="text">
						<text class="price">￥{{price}}</text>
						<view class="num">
							<button>-</button>
							<button style="width: 80rpx;">1</button>
							<button>+</button>
						</view>
					</view>
				</view>
			</view>
			
			<view class="kong">
				
			</view>
		</view>
		<view class="kong">
			
		</view>
		<view class="box1">
			<view class="shop">
				<view class="dian">
					<a :class="name1"  href="" @click.prevent="ClickFunction($event)"></a>
				</view>
				<view class="iconfont icon-shangpu" style="font-size: 30px; margin-top: -10rpx; margin-left: 20rpx; "></view>
				<text class="content">小米自营店</text>
				<view class="iconfont icon-jinrujiantou" style=" font-size: 32px; margin-top: -10rpx;"></view>
			</view>
			<view class="good">
				<view class="dian">
					<a :class="name1"  href="" @click.prevent="ClickFunction($event)"></a>
				</view>
				<image class="img" style="width: 300rpx; height: 250rpx; margin-top: -20px; " src="https://img12.360buyimg.com/n7/jfs/t1/142860/9/29604/48781/633505c6E883fcda6/87d60f96172b8829.jpg" mode=""></image>
				<view class="">
					<text>小米12S Pro 骁龙8+ 徕卡专业光学镜头 5G智能拍照手机 绿色</text>
					<view class="text">
						<text class="price">￥{{price1}}</text>
						<view class="num">
							<button>-</button>
							<button style="width: 80rpx;">1</button>
							<button>+</button>
						</view>
					</view>
				</view>
				
			</view>
		</view>
		<view class="box3">
			<view class="dian">
				<a :class="name2"  href="" @click.prevent="ClickFunctionall($event)"></a>
			</view>
			<text class="text1">全选</text>
			<text class="text2">合计：</text>
			<text class="price">￥{{priceall}}</text>
			<view class="all">
				结算
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				name:"yuan",
				name1:"yuan",
				name2:"yuan",
				price1:4500,
				price:9000,
				priceall:0
			}
		},
		methods: {
			Function(e){
				if(this.name == "yuan"){
					this.name = "yuan1"
					console.log(this.priceall = this.priceall+this.price)
					if(this.name == "yuan1" && this.name1 == "yuan1"){
						this.name2="yuan1"
					}else{
						this.name2 = "yuan"
					}
				}else{
					this.name = "yuan"
					console.log(this.priceall = this.priceall - this.price)
					this.name2 = "yuan"
				}
				
			},
			ClickFunction(e){
				if(this.name1 == "yuan"){
					this.name1 = "yuan1"
					console.log(this.priceall = this.priceall+this.price1)
					if(this.name == "yuan1" && this.name1 == "yuan1"){
						this.name2="yuan1"
					}else
						this.name2 = "yuan"
				}else{
					this.name1 = "yuan"
					console.log(this.priceall = this.priceall-this.price1)
					this.name2 = "yuan"
				}
				
			},
			ClickFunctionall(e){
				if(this.name2 == "yuan1"){
					this.name2 = "yuan"
					this.name = "yuan"
					this.name1 = "yuan"
					this.priceall=0
				}else{
					this.name2 = "yuan1"
					this.name = "yuan1"
					this.name1 = "yuan1"
					this.priceall = this.price + this.price1
					console.log(this.priceall)
				}
				
				
				
			},
		},
		
	}
</script>

<style>
	.shop{
		padding: 15px;
		display: flex;
		border-bottom: 1px solid #eee;
		.content{
			margin-left: 20rpx;
			font-size: 32rpx;
		}
		
	}
	.good{
		display: flex;
		padding: 15px;
		height: 250rpx;
		box-sizing: border-box;
		.dian{
			margin-top: 75rpx;
		}
		.text{
			display: flex;
			.price{
				color: red;
				margin-top: 50rpx;
			}
			.num{
				margin-top: 50rpx;
				margin-left: 110rpx;
				display: flex;
			}
			
		}
		
	}
	.box3{
		width: 100%;
		height: 200rpx;
		position: fixed;
		bottom: 0;
		display: flex;
		box-sizing: border-box;
		.dian{
			margin-top:40rpx;
		},
		.text1{
			font-size: 35rpx;
			margin-top: 20px;
			margin-right: 90px;
			margin-left: 20px;
			
		}
		.text2{
			margin-top: 20px;
		}
		.price{
			margin-top: 20px;
			margin-right: 30px;
			color: red; 
		}
		.all{
			background-color: red;
			height: 100%;
			width: 100px;
			color: #fff;
			text-align: center;
			line-height: 100rpx;
			position:absolute;
			right: 0;
		}
		.all:hover{
			cursor: pointer;
		}
		
	}
	.yuan{
		width: 40rpx;
		height: 40rpx;
		border: 1px solid #000;
		border-radius: 50%;
		display: block;
		
	}
	.yuan1{
		
		width: 40rpx;
		height: 40rpx;
		border-radius: 50%;
		display: block;
		background-color: red;
		box-sizing: border-box;
		border: 1px solid red;
		
	}
	.kong{
		width: 100%;
		height: 15rpx;
		background-color: #eee;
		border-radius: 3px;
		box-sizing: border-box;
	}
	button{
		display: block;
		font-size: 10rpx;
		opacity: 0.4;
		border-radius: 0%;
		
	}
	
</style>
