<template>
	<view>
		<view>
			<text class="">实例1</text>
			<view class="mt-4">
				<movable-area  class="bg-primary mb-4" style="height:300rpx; width:100vw;">
					<movable-view :x="x" :y="y" direction="all" class="bg-danger" style="height:100rpx; width:100rpx;" @click="change"></movable-view>
				</movable-area>
				
				<view @click="tap">点击这里</view>
			</view>
			
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				x: 0,
				y: 0,
				scale: 2,
				old: {
					x: 0,
					y: 0,
					scale: 2
				}
			}
		},
		methods: {
			change(e){
				this.old.x = e.detail.x
				this.old.y = e.detail.y
			},
			tap(){
				this.x = this.old.x
				this.y = this.old.y
				this.$nextTick(function(){
					this.x=30
					this.y=30
				})
			}
		}
	}
</script>

<style>

</style>
