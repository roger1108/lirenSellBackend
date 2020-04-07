# 《SpringBoot微信点餐》常见问题

问：关于账号借用问题

答：提问区已经有这个问题了，http://coding.imooc.com/learn/questiondetail/17686.html



问： HTML5<audio>报错Uncaught (in promise) DOMException解决方法

答： 上述错误是由于Chrome浏览器禁止了音频自动播放，按下边方法可解决限制：
·在Chrome地址栏输入chrome://flags/#autoplay-policy并打开；
·将autoplay-policy选项值设置为no user gesture is required；
·点击页面最下方"Relaunch Now"重启浏览器生效； 


问：取消订单也需要提醒

答：正在开发  ，在list.ftl里面可以新增一个弹窗“cancelModal” , orderServiceImp 里cancel(OrderDTO)方法里加上websocket推送， 另外断线重连(ping pong) 模式也需要下一步考虑。 (记得发布的时候websocket地址修改)



问：如何部署

答： 前端部署  npm run build  (开发调试是npm run dev)  -->dist的内容 部署到nginx服务器   116.62.172.49 /usr/local/nginx/1.6.3/    conf目录下是配置(vhosts 和 反向代理) sbin目录下 ./nginx -t 检测配置是否语法正确，   ./nginx -s reload 重新启动
后端部署 mvn clean package (skip test)  --> sell.jar 包 部署到服务器  101.37.149.241 /root/liren_project

Git--将已有的项目添加到github https://blog.csdn.net/north1989/article/details/53471439