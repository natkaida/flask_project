title: Flask с нуля
date: 2022-06-14
description: Функции представления и маршруты
tag: flask
project: Курс по Flask для начинающих
platform: Flask Практикум
link: http://example.com

Начать знакомство с Flask можно с создания простого приложения, которое выводит “Hello World”. Создаем новый файл main.py и вводим следующий код.

	from flask import Flask

	app = Flask(__name__)

	@app.route('/')
	def index():
	    return 'Hello World'

	if __name__ == "__main__":
	    app.run()

Это приложение “Hello World”, созданное с помощью фреймворка Flask. Чтобы запустить main.py, нужно выполнить следующую команду:

	(env) python main.py
	Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
