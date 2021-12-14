# autoRecoder
本项目通过读取环境变量中的信息，进行奕辅导的自动化打卡,依次执行如下信息：
- 使用抓包软件获取`accessToken`
- 到[server酱](https://sct.ftqq.com/)去注册并获取一个SendKey,然后写入github关键字为`secret`
- 写入地理位置的经度信息`latitude`:湖南工商大学的经度为：28.221294
- 写入地理位置的纬度信息`longitude`：湖南工商大学的纬度为：112.919075
- 写入省份`province`：湖南省
- 写入城市`city`: 长沙市
- 写入区`area`: 岳麓区
- 写入地址信息`address`：湖南省长沙市岳麓区湖南工商大学
## usage
**强烈建议使用自动执行**
### github actions 自动执行

配置文件在[python-app.yml](https://github.com/TobiasHu2021/autoRepoter/blob/main/.github/workflows/python-app.yml)中修改cron选项中的时间配置，目前配置为每天北京时间08点02分15秒执行一次

#### github action 配置
* fork本项目
* 在自己的repo下Settings/Screts中设置`accessToken`, `secret`, `latitude`, `longitude`, `province`, `city`, `area` 和 `address`。具体写法上面有样例
* 【可选】如果需要微信通知，可以配置FT_SCKEY,为[ftqq微信推送服务](http://sc.ftqq.com/?c=code)中的sckey
* fork的项目默认是关闭的，需要手动点击repo页的actions以enable