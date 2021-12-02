<template>
	<view>
		<view>
			<view v-if="!hasLeftWindows">
				<view class="mb-4" v-for="(item,index) in list" :key="item.id">
					<view>
						<view class="tit p-4 bg-white" @click="triggercollapse(index)" :class="item.open ? 'active' : ''">{{item.name}}</view>
						<view v-show="item.open" class="ite p-4 bg-white" v-for="(value,index1) in item.pages" @click="godetailPage(value)">
							{{value.name ? value.name :　value}}
						</view>
					</view>
					
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		watch: {
			$route: {
				immediate: true,
				handler(newRoute) {
					console.log(newRoute)
				}
			}
		},
		data() {
			return {
				hasLeftWindows:false,
				list:[{
								id: 'view',
								name: '视图容器',
								open: false,
								pages: [
									'view',
									'scroll-view',
									'swiper'
									// #ifndef MP-TOUTIAO || MP-LARK
									,
									'movable-view',
									'cover-view'
									// #endif
								]
							}, {
								id: 'content',
								name: '基础内容',
								open: false,
								pages: ['text', 'rich-text', 'progress']
							}, {
								id: 'form',
								name: '表单组件',
								open: false,
								pages: ['button', 'checkbox', 'form', 'input', 'label', 'picker', 'picker-view', 'radio',
									'slider',
									'switch', 'textarea',
									// #ifdef APP-PLUS || MP-WEIXIN || H5
									'editor',
									// #endif
								]
							}, {
								id: 'nav',
								name: '导航',
								open: false,
								pages: ['navigator']
							}, {
								id: 'media',
								name: '媒体组件',
								open: false,
								pages: [
									'image',
									'video'
								],
							},
							// #ifndef MP-TOUTIAO || MP-KUAISHOU
							{
								id: 'map',
								name: '地图',
								open: false,
								pages: ['map']
					
							},
							// #endif
							// #ifndef QUICKAPP-WEBVIEW-UNION
							{
								id: 'canvas',
								name: '画布',
								open: false,
								pages: ['canvas']
							},
							// #endif
							// #ifdef APP-PLUS || H5
							{
								id: 'web-view',
								name: '网页',
								open: false,
								pages: [{
									name: '网络网页',
									url: '/pages/component/web-view/web-view'
								}, {
									name: '本地网页',
									url: '/pages/component/web-view-local/web-view-local'
								}]
							},
							// #endif
							// #ifndef APP-PLUS || H5 || MP-LARK
							{
								id: 'web-view',
								name: '网页',
								open: false,
								pages: ['web-view']
							},
							// #endif
							// #ifndef H5 || MP-BAIDU || QUICKAPP-WEBVIEW || MP-LARK
							{
								id: 'ad',
								url: 'ad',
								name: 'AD组件',
								open: false
							},
							// #endif
						]
			}
		},
		methods: {
			triggercollapse(index){
				for(let i=0; i<this.list.length; i++){
					if(i===index){
						this.list[index].open = !this.list[index].open;
					}else{
						this.list[i].open = false;
					}
				}
			},
			godetailPage(value){
				const url = '../../components/'+ value + '/' + value;
				if(typeof value === 'string'){
					console.log(url)
					uni.navigateTo({
						url:url,
						success(res) {
							console.log(res);
						},
							fail(err) {
								console.log(err);
							}
						});
				}else{
					uni.navigateTo({
						ul:value.url
					})
				}
				
			}
		}
	}
</script>

<style>
.ite{
	border-top:1px solid #ccc;
}

</style>
