# NB
import re
import urllib.request
url='http://maoyan.com/board/4?offset=0'
re1=urllib.request.urlopen(url)
html=re1.read()
pattern=re.compile('<dd>.*?name"><a.*?">(.*?)</a>.*?star">(.*?)</p>.*?</dd>',re.S)
html=html.decode('utf-8')
items=re.findall(pattern,html)
for item in items:
    xy = {}
    xy['名称'] = item[0]
    xy[''] = item[1]
    print(xy)
