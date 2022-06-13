<template>
	<view class="content flex-center">
	  <view class="bg flex-center">
			<view class="ip">
				<button class="mgb-50" @click="createRoom">创建房间</button>
				<button>加入房间</button>
			</view>
	  </view>
	</view>
</template>

<script>
  import io from '@hyoga/uni-socket.io';
	
	export default {
		data() {
			return {

			}
		},
		onLoad() {

		},
		methods: {
			createRoom () {
				
			}
		}
	}
</script>

<style lang="scss">
.content {
	width: 100%;
	height: 100vh;
	.bg {
	  width: 100%;
		height: 95%;
		background: url("https://s1.ax1x.com/2022/06/13/XRBITU.jpg") center/cover no-repeat;
		.ip {
			width: 65%;
			height: 250rpx;
			button {
				width: 65%;
				box-shadow: 1px 1px 1px 1px gray;
			}				
		}
	}
}
</style>
