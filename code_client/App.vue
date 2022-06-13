<script>
	export default {
		data () {
			return {
				APPID: "wx9aa61faf9cdefdf8",
				APPSECRET: "3b480d6c25f9acb8152333459b1d072f"
			}
		},
		onLaunch: function() {
			console.log('App Launch')
			// #ifndef H5
			uni.authorize({
			    scope: 'scope.userInfo',
			    success() {
			        uni.getUserInfo({
			              provider: 'weixin',
			              success: function (infoRes) {
			                console.log('用户昵称为：' + infoRes.userInfo.nickName);
			              }
			        });
			    }
			})
			
			uni.login({
			  provider: 'weixin',
				onlyAuthorize:true,
			  success: ({code}) => {
			    this.$reqGet({
						url:  `https://api.weixin.qq.com/sns/jscode2session?appid=${this.APPID}&secret=${this.APPSECRET}&js_code=${code}&grant_type=authorization_code`,
						rsv: (data) => {
							uni.showToast({
								title: JSON.stringify(data.openid)
							})
							console.log(data)
						}
					})
			  }
			});
			
// uni.login({
//   provider: 'weixin',
//   success: function (loginRes) {
//     console.log(loginRes.authResult);
//     // 获取用户信息
//     uni.getUserInfo({
//       provider: 'weixin',
//       success: function (infoRes) {
// 				console.log(infoRes)
//         console.log('用户昵称为：' + infoRes.userInfo.nickName);
//       }
//     });
//   }
// });
			// #endif
			
			// #ifdef H5
			// #endif
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style lang="scss">
	@import url("@/style/base.scss");
	/*每个页面公共css */

</style>
