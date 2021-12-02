<template>
	<view>
		<swiper class="swiper" circular :autoplay="autoPlay" :indicator-dots="indicatorDots" :interval="interval" :duration="duration">
			<swiper-item>
				<view class="swiper-item bg-danger">A</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item bg-success">B</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item bg-primary">C</view>
			</swiper-item>
		</swiper>
		
		<view class="flex justify-between py-3 align-center" style="border-bottom:1px solid #ccc">
			<text>指示点</text>
			<switch :checked="indicatorDots" @change="changeIndicatorDots" />
		</view>
		<view class="flex justify-between py-3 align-center" style="border-bottom:1px solid #ccc">
			<text>自动播放</text>
			<switch :checked="autoPlay" @change="changeAutoPlay" />
		</view>
		<view class="px-4">
			<view class="flex justify-between my-5">
				<text>幻灯片时长(ms)</text>
				<text>500</text>
			</view>
			<slider min="500" max="2000" :value="duration" @change="speed"/>
		</view>
		
		<view class="px-4">
			<view class="flex justify-between my-5">
				<text>自动播放时间(ms)</text>
				<text>1000</text>
			</view>
			<slider min="1000" max="4000" :value="interval" @change="changeInterval"/>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				indicatorDots:true,
				autoPlay:true,
				duration:1000,
				interval:2000
			}
		},
		methods: {
			changeIndicatorDots(){
				this.indicatorDots=!this.indicatorDots
			},
			changeAutoPlay(){
				this.autoPlay = !this.autoPlay
				console.log(this.autoPlay)
			},
			speed(e){
				const value = e.detail.value;
				this.duration = value;
			},
			changeInterval(e){
				const value = e.detail.value;
				this.interval = value;
			}
		}
	}
</script>

<style>
.swiper{
	height:300rpx;
}
.swiper-item{
	line-height:300rpx;
	text-align:center;
	display:block;
	color:white;
	height:300rpx;
}
</style>
