# infra_sprint1

Социальная сеть с возможностью выкладывать фото котиков и описывать их достижения.

Шаблон заполнения .env:
SECRET_KEY
DEBUG
ALLOWED_HOSTS

Стек: Python 3.9, Docker, Nginx, PostgreSQL, Gunicorn, GitHub Actions

Запуcк проекта:
   1) скопировать проект с github  ```python git clone git@github.com:Your_account/infra_sptint1.git``` 
   2) Установите менеджер пакетов и утилиту виртуальной среды ```python sudo apt install python3-pip python3-venv -y ```
   3) создайте виртуальное оеружение ```python python3 -m venv venv``` 
   4) активируйте виртуальное окружение ```python source venv/bin/activate ``` 
   5) установите зависимости ```python pip install -r requirements.txt ```
   6) выполните миграции ```python python manage.py migrate```
   7) создайте супрепользователя ```python python manage.py createsuperuser```
   8) запуск frontend
      ```python curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash - &&\ sudo apt-get install -y nodejs```
      в директории ```python <ваш проект>/frontend/``` выполнитe ```python npm i```
   9) запуск gunicorn
      ```python pip install gunicorn==20.1.0```
      ```python sudo nano /etc/systemd/system/gunicorn.service```
   10) запуск Nginx
      ```python sudo apt install nginx -y```
      ```python sudo ufw allow 'Nginx Full'```
      ```python sudo ufw allow OpenSSH```
      ```python sudo ufw enable```
   11) сбор статики
      в директорр ```python <имя_проекта>/frontend/``` выполнить ```python npm run build```
      ```python sudo nano /etc/nginx/sites-enabled/default``` # поправить содержимое
      ```python sudo systemctl reload nginx```
