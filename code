# -*- coding: utf-8 -*-
"""
Created on Wed Dec  6 13:28:03 2017

@author: Administrator
"""
import requests
from bs4 import BeautifulSoup


def article(xiaoshuo):
    
    req = requests.get(xiaoshuo)
    soup = BeautifulSoup(req.text,'html.parser')
    aa = soup.select(".showtxt")[0]
    return aa.text.replace("\xa0"*8,"\n")
def baocun(AA):
    with open(r'd:\xiaoshuo','a+') as f:
        f.write(AA)

url = "http://www.biqukan.com/1_1094/"
req = requests.get(url)
soup = BeautifulSoup(req.text,'html.parser')
aa = soup.select(".listmain a")
for i in aa:
    print(i.text)
    neirong = article("http://www.biqukan.com" + i['href'])
    try:
        baocun(i.text + str(neirong))
    except UnicodeEncodeError:
        print("存入错误")
        pass
