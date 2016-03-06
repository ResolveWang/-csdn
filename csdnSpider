# -*- coding: utf-8 -*-

import requests
from bs4 import BeautifulSoup

requests.Session()

hea = {"User-Agent":"Mozilla/5.0 (Windows NT 6.3; WOW64; Trident/7.0; rv:11.0) like Gecko","Accept-Language":"zh-CN,zh;q=0.8"}
first_url = "https://passport.csdn.net/account/login?from=http://my.csdn.net/my/mycsdn"
#请求的时候如果不带头信息的话会出现403错误
html = requests.get(first_url,headers=hea).text

soup = BeautifulSoup(html,'html.parser')
form = soup.find("form")
LT = form.find(attrs={"name":"lt"}).attrs['value']
jsessionid = form.attrs['action'][26:66]
username = '1796246076@qq.com'
password = 'wang1204'
execution = 'e1s1'
_eventId = 'submit'
lt = LT

login_url = "https://passport.csdn.net/account/login;jsessionid="+jsessionid+"?from=http://my.csdn.net/my/mycsdn"
print(login_url)
post_data = {"username":username,"password":password,"lt":LT,"execution":execution,"__eventId":_eventId}
print(post_data)
rs = requests.post(login_url,data=post_data,headers=hea)


mycsdn_url = "http://my.csdn.net/"
mycsdn = requests.get(mycsdn_url,headers=hea).text
print(mycsdn)
