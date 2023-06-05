# piaoxingqiu

票星球自动抢票


1.配置config.py

  showid怎么拿？
  
  浏览器打开票星球网站，点击进入具体演出项目详情页面，地址栏最后24位字符串即为showid，如：
  
  https://m.piaoxingqiu.com/content/641ae55ac3f25b0001d06286
  
  641ae55ac3f25b0001d06286就是show_id
  
  
  session_id怎么拿？
  
  浏览器输入以下地址，将中间的24位字符串替换为刚才拿到的show_id
  
  https://m.piaoxingqiu.com/cyy_gatewayapi/show/pub/v3/show/641ae55ac3f25b0001d06286/sessions_static_data
  
  找到自己想看的那个场次，然后找到该场次对应的bizShowSessionId字段，后面的字符串即是session_id
  
  (个人建议可以不填，让系统自动刷，刷到哪场算哪场，目前的逻辑是，如果用户指定了场次，则会先刷这一场的票，如果该场次缺票，系统会自动去刷其他场次的票，而不会重复刷这一场)
  
  
  token怎么拿？
  
  先登陆，然后按F12，选择Network，选择Fetch/XHR，然后进入任意演出详情，Network的Name下面会出现很多条请求，点击任意一个，然后找到 Headers -> Request Headers -> Access-Token，后面很长的字符串就是token
  
  

2.运行main.py

  python main.py
  
  
后续工作：

1.目前仅支持[无需选座]的演出，暂不支持自己选座的，后续优化支持

2.目前是人工提前几秒启动程序开始循环刷票，这样就会导致用户自己指定的sessio_id不起作用，后续考虑增加定时抢票功能

  
免责申明

该项目仅供学习参考，切勿用于商业用途
