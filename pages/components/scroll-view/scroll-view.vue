<template>
	<view>
		<view class="flex flex-column">
			<text>Vertical Scroll</text>
			<text class="font-sm mt-2">纵向滚动</text>
		</view>
		<view class="text-center mt-3 text-white"  style="line-height:300rpx;">
			<scroll-view scroll-y="true" @scroll="scroll"  :scroll-top="scrollTop" class="scroll-Y">
				<view class="scroll-item bg-danger">6</view>
				<view class="scroll-item bg-success">7</view>
				<view class="scroll-item bg-primary">8</view>
			</scroll-view>
		</view>
		<view @tap="goTop" class=" mt-5 text-center">
			点击这里返回顶部
		</view>
		
		<view class="mt-5">
			<view class="flex flex-column">
				<text>Horizontal Scroll</text>
				<text class="font-sm mt-2">横向滚动</text>
			</view>
			<view class="text-center mt-3 text-white"  style="line-height:300rpx;">
				<scroll-view scroll-x="true" @scroll="scroll" scroll-left="120"  class="scroll-X">
					<view class="scroll-item1 bg-danger">6</view>
					<view class="scroll-item1 bg-success">7</view>
					<view class="scroll-item1 bg-primary">8</view>
				</scroll-view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				scrollTop:0,
				old:{
					scrollTop:0
				}
			}
		},
		methods: {
			scroll:function(e){
				this.old.scrollTop = e.detail.scrollTop
			},
			goTop:function(){
				this.scrollTop = this.old.scrollTop
				this.$nextTick(function(){
					this.scrollTop=0;
				})
				uni.showToast({
					title:"已滚动到顶部",
					icon:"none"
				})
			}
		}
	}
</script>

<style>
.scroll-Y{
	height:300rpx;
}
.scroll-item{
	height:300rpx;
}
.scroll-X{
	white-space: nowrap;
}
.scroll-item1{
	display:inline-block;
	width:100%;
}
</style>
