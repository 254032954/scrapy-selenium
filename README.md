# scrapy-selenium
用python对接scrapy进行网易云歌单爬取
本次爬取是网易云音乐对应的歌单，是为了试验scrapy对接selnium的这样的一个方法验证。
主要注意一下几点：
    1.本次用的是driver.Chrome()来爬取的并没有用Phantomjs为了方便查看是否可以生成网址循环。
    2.对接selenium爬取网易云音乐的是否需要进行driver.switch_to_frame("g_iframe")的操作。
    3.存储的数据库为mongdb数据库
    4.用urljoin来构造下一页的url主要在获取节点的时候对应的是div#m-pl-pager a:nth-child(12)
      next_url = response.css('div#m-pl-pager a:nth-child(12)::attr(href) ').extract_first()  # 下一页网址的连接，进行翻页操作
      next_url = response.urljoin(next_url)
      
    
    
