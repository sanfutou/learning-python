**1、在自己搭建的django网站中setting中找到找到ALLOWED\_HOSTS=\[ \]，在中括号中加入你在局域网中的IP，ALLOWED\_HOSTS=\[ ’192.168.1.155’\]。**

**2、在网站目录中运行Python manage.py runserver 192.168.1.155:8000，这样在局域网内就可以访问你的网站了。**

