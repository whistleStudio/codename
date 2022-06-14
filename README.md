## Dev Log

### [06131734]

- client  

（"@hyoga/uni-socket.io": "^3.0.4"）

1 初始首页样式

2 封装了部分请求接口，但关于微信登录授权还需再测试

- server

1 启动websocket服务

### [06141731]

- client

安装了uview

1 因为小程序即将废除getUserInfo和getUserProfile 文档

改用【头像昵称填写】方法 https://developers.weixin.qq.com/miniprogram/dev/framework/open-ability/userProfile.html

2 上部POP用于填写昵称, 样式不要直接加在引用的组件上，u-popup小程序里显示就有问题

3  修改了app.vue逻辑， login -> 获得code -> 携带code访问后台 -> 后台访问微信服务器返回session和openid ->     设置状态机nickname和avatar 可以再修改下

- server

 安装node-fetch

1 logApi若干请求

2 建立mongo数据库codename以及user模型