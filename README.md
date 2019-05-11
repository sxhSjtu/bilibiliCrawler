# bilibiliCrawler
注意事项:

####################

请勿将该程序用于任何非法或灰色行为，作者对此不承担任何责任

####################
0.在运行crawler.py这一爬虫程序前, 请确认您的python环境为python3, 并安装了requests, 该程序仅能在命令提示符（cmd）中运行

1.爬虫速度过快会被封IP，估计速度上限高于 8条数据/秒 ，请勿超过太多。速度可由各同时运行的爬虫给出的抓取频率相加而得,抓取 频率将在每次文件保存完毕后出现。

2.采集的数据依次为：av号、分区号、二级分区号、标题、发布时间、视频时长、up主ID、up主昵称、播放量、弹幕量、回复量、收藏量、投币量、分享量、喜欢量、不喜欢量。

3.本程序将同时运行多个爬虫(我同时运行4个),并在某一个爬虫进程内将数据分别存入不同的csv文件中。

4.本程序无正常退出方式，只能等待其完成任务自行退出。强行关闭程序将导致当前正在写入的单个文件数据全部丢失。
但是不会影响已写完保存的文件。这也是将数据放入许多不同文件的原因。

5.运行中若出现“200”或“0”字样，则代表程序运转正常，若出现“403”字样，则代表由于抓取速度过快，你的IP已被网站封掉。
请减小同时运行的爬虫个数，并等待一段时间直至IP解封(一个多小时左右)，或切换wifi以更改新的IP。查看解封与否可通过在浏览器输入   https://api.bilibili.com/x/web-interface/view?aid=7  来判断。若看见   {code:0,message:0,ttl:1,data:{aid:7,videos:1    等字样，代表已解封，其余页面均为未解封。

6.程序中安排了周期性的休眠时间，这是反-反爬虫策略，不是程序卡了(当然如果几十秒都不动，那就是真的卡了……)如果你想修改休 眠时长，请修改源代码中的time.sleep()参数
7.文件打开方式为a,即添加，所以注意不要让新一次的程序运行生成的数据接着写入旧文件中
