<template>
	<view>
		
		<view>
			<view class="title my-3">flex-direction:row</view>
			<text class="font-sm">横向布局</text>
			<view class="flex justify-between text-center text-white mt-3" >
				<view class="flex-1  bg-danger" style="height:250rpx; line-height:250rpx">A</view>
				<view class="flex-1  bg-success" style="height:250rpx; line-height:250rpx">B</view>
				<view class="flex-1  bg-primary" style="height:250rpx; line-height:250rpx">C</view>
			</view>
		</view>
		
		<view>
			<view class="title my-3">flex-direction:column</view>
			<text class="font-sm">纵向布局</text>
			<view class="flex flex-column  justify-between text-center text-white mt-3" >
				<view class="flex-1  bg-danger" style="height:150rpx; line-height:150rpx">A</view>
				<view class="flex-1  bg-success" style="height:150rpx; line-height:150rpx">B</view>
				<view class="flex-1  bg-primary" style="height:150rpx; line-height:150rpx">C</view>
			</view>
		</view>
		
		<view>
			<view class="title my-3">更多布局演示</view>
			<text class="font-sm">flex 布局演示</text>
			<view class="dipflex text-center font-sm flex flex-column">
				<view class="bg-hover-light text-center mt-3 flex-1">纵向布局-自动宽度</view>
				<view class="bg-hover-light text-center mt-3" style="width:350rpx;">纵向布局-自动宽度</view>
				<view class="flex mt-3">
					<view class="bg-hover-light text-center px-2">横向布局-自动宽度</view>
					<view class="bg-hover-light text-center ml-3 px-2">横向布局-自动宽度</view>
				</view>
				
				<view class="flex   mt-3 justify-center">
					<view class="bg-hover-light text-center px-2">横向布局-居中</view>
					<view class="bg-hover-light text-center ml-3 px-2">横向布局-居中</view>
				</view>
				
				<view class="flex mt-3 justify-end">
					<view class="bg-hover-light text-center px-2">横向布局-居右</view>
					<view class="bg-hover-light text-center ml-3 px-2">横向布局-居右</view>
				</view>
				
				<view class="flex   mt-3 justify-end">
					<view class="bg-hover-light text-center px-2 flex-1">横向布局-平均分布</view>
					<view class="bg-hover-light text-center ml-3 px-2 flex-1">横向布局-平均分布</view>
				</view>
				
				<view class="flex   mt-3 justify-between">
					<view class="bg-hover-light text-center px-2">横向布局-两端对齐</view>
					<view class="bg-hover-light text-center ml-3 px-2">横向布局-两端对齐</view>
				</view>
				
				<view class="flex   mt-3 justify-between">
					<view class="bg-hover-light text-center px-2" >横向布局-固定宽度</view>
					<view class="bg-hover-light text-center ml-3 px-2 flex-1">横向布局-占满余量</view>
				</view>
				
				<view class="flex   mt-3 justify-between">
					<view class="bg-hover-light text-center px-5" style="width:130rpx" >固定宽度</view>
					<view class="bg-hover-light text-center ml-3 px-2 flex-1">自动占满</view>
					<view class="bg-hover-light text-center  ml-3 px-5" style="width:130rpx"  >固定宽度</view>
				
				</view>
				
				<view class="flex   mt-3 justify-between">
					<view class="bg-hover-light text-center px-5" style="height:180rpx" >垂直居顶</view>
					<view class="flex align-center bg-hover-light justify-center  ml-3 px-2 flex-1" style="height:180rpx"><text>垂直居中</text></view>
					<view class="flex bg-hover-light text-center align-end  ml-3 px-5" style="height:180rpx"  >
						<text>垂直居低</text>
					</view>
				
				</view>
				
			</view>
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

<style>
.dipflex view{
	height:100rpx;
	line-height:100rpx;
}
</style>
