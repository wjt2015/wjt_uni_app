<template>
	
	<view class="content">
		
<!-- 		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view> -->
		
			<view>
				<view style="background: #4CD964;width: 300rpx;color:#DD524D;" class="title"></view>
					<label>hello uni-app!</label>
					<hr/>
					<label>android手机测试!</label>
					<input type="text" class="text-area" value="请输入" />
					<br/>
					<button type="primary">按一按</button>
				</view>
			</view>
			
		</template>
		
		
	</view>
	


<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
