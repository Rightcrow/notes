## Python



### Django

<img src="C:%5CUsers%5Czhang%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20200508210509149.png" alt="image-20200508210509149" style="zoom: 50%;" />



#### 基本配置

| （1）创建django项目 | $django-admin startproject {name} |
| ------------------- | --------------------------------- |
| (2) 启动项目        | $python manage.py runserver       |
| (3) 添加项目应用    | $python manage.py startapp {name} |



#### 数据模型类

> 处于models.py中
>
> 与数据库中数据表对应



##### models配置

```python
from django.db import models
from django.utils import timezone
from django.contrib.auth.models import User

class BlogArticles(models.Model):
    title = models.CharField(max_length=300)//规定字段最大长度
    
    //models.cascade级联删除
    author = models.ForeignKey(User,on_delete=models.CASCADE,related_name="blog_posts")
 
    body = models.TextField()
    publish = models.DateTimeField(default=timezone.now)

    class Meta:
        ordering = ("-publish"，)

    def __str__(self):
        return self.title
```

> 根据models建立数据库表

```shell
$python manage.py makemigrations

$python manage.py migrate
```

> app要在setting中设置

![image-20200509091905956](https://i.loli.net/2020/05/09/NLv3b59sIQhipeT.png)



##### 发布博客文章

> 创建超级管理员

```
python manage.py createsuperuser
Username:admin
Emal address: admin@admin.com
Password:12345678

```





