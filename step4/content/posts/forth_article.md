title: Продвинутый Django 
date: 2022-06-16
description: Разбираемся с ORM в Django и работаем с базой без SQL-запросов
tag: django
project: Курс по Django - уровень 2
platform: Django Практикум
link: http://example.com

Django ORM (Object Relational Mapping) является одной из самых мощных особенностей Django. Это позволяет нам взаимодействовать с базой данных, используя код Python, а не SQL.

Для демонстрации опишу такую модель:

	from django.db import models

	class Blog(models.Model):
	    name = models.CharField(max_length=250)
	    url = models.URLField()

	    def __str__(self):
	        return self.name

	class Author(models.Model):
	    name = models.CharField(max_length=250)

	    def __str__(self):
	        return self.name

	class Post(models.Model):
	    title = models.CharField(max_length=250)
	    content = models.TextField()
	    published = models.BooleanField(default=True)
	    blog = models.ForeignKey(Blog, on_delete=models.CASCADE)
	    authors = models.ManyToManyField(Author, related_name="posts")
