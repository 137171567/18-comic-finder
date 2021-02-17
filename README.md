# 禁漫天堂下载器

使用java的禁漫天堂爬虫🤡

java这门语言能让小项目变成中项目, 中项目变成大项目 🤡

没什么牛逼的地方, 就是春节假期图一乐🤡

## 打包程序

1. 安装jdk15.

2. 安装maven.

3. 下载源代码并且修改application.properties文件中的以下4个配置, 第一个是爬虫存放图片的路径, 第二第三个是科学上网的ip和端口, 因为禁漫天堂是被墙的不设置代理应该下载不下来, 第四个是访问禁漫天堂时候浏览器的cookie

   ```properties
   comic.download.path=C:\\Users\\jiayao\\Pictures
   comic.proxy.host=127.0.0.1
   comic.proxy.port=10808
   comic.download.cookie=__cfduid=d143120c4820765e39f93c708adb046db1613394311; AVS=lst54bj7248ch7r16rp8fo7800; shunt=1; _gid=GA1.2.1192332230.1613394323; cover=1; ipcountry=HK; ipm5=c759e3424d3ed099c2a82ef7f5222a99; _ga_YYJWNTTJEN=GS1.1.1613463242.7.1.1613464015.58; _ga=GA1.2.1275815841.1613394321; _gali=wrapper
   ```
4.执行`mvn clean install` 得到最后的jar包

如果直接下载我提供的jar包, 解压后修改上面四个配置再压缩成jar包

## 运行程序

在确保已经有java运行环境之后, 命令行中进入jar包所在的目录, 执行`java -jar ./*.jar`即可运行程序 

## 下载漫画

运行程序之后打开浏览器, 在地址栏输入 :

```url
http://localhost:7788/finder/download?homePage=你想要下载的漫画主页
```

即可开始下载, 例如

```
http://localhost:7788/finder/download?homePage=https://18comic.vip/album/177680
```

注意漫画的主页一定是有album这个单词的, 如果你的url里面出现了photo说明不是主页, 而是某个章节的页面.

## 项目特点

- 没有用到爬虫库, 纯用hutool对html页面进行切分.
- 多线程异步爬虫.
- 对2020-10-27之后的反爬虫图片进行了反反爬虫处理.

## TODO

- [ ] 支持单独下载某个章节而不是每一次都下载完整的一本漫画.
- [ ] 直接生成exe文件不需要依赖jdk环境.
- [ ] 通过集成邮件服务, 每一章都发一封邮件? 邮件里面是这这一章的全部图片.