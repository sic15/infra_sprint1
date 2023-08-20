# infra_sprint1

Социальная сеть с возможностью выкладывать фото котиков и описывать их достижения.

Шаблон заполнения .env:
SECRET_KEY
DEBUG
ALLOWED_HOSTS

Стек: Python 3.9, Docker, Nginx, PostgreSQL, Gunicorn, GitHub Actions

Запуcк проекта:
1) ```python
   git clone git@github.com:Your_account/infra_sptint1.git``` # скопировать проект с github
1) sudo apt install python3-pip python3-venv -y # Установите менеджер пакетов и утилиту виртуальной среды
2) python3 -m venv venv # создайте виртуальное оеружение
3) source venv/bin/activate # активируйте виртуальное окружение
4)pip install -r requirements.txt # установите зависимости
5) python manage.py migrate # выполните миграции
6) python manage.py createsuperuser
7) запуск frontend
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash - &&\ sudo apt-get install -y nodejs
в директории <ваш проект>/frontend/ выполнить npm i
8) запуск gunicorn
pip install gunicorn==20.1.0
sudo nano /etc/systemd/system/gunicorn.service # заполнить файл
9) запуск Nginx
sudo apt install nginx -y
sudo ufw allow 'Nginx Full'
sudo ufw allow OpenSSH
sudo ufw enable
10) сбор статики
в директорр <имя_проекта>/frontend/ выполнить npm run build
sudo nano /etc/nginx/sites-enabled/default # поправить содержимое
sudo systemctl reload nginx
