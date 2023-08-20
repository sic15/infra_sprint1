# infra_sprint1

## Описание проекта 

Социальная сеть с возможностью выкладывать фото котиков и описывать их достижения.

---
## Стек 

Python 3.9, Docker, Nginx, PostgreSQL, Gunicorn, GitHub Actions

---

## Запуcк проекта: 

   1) скопировать проект с github  `git clone git@github.com:Your_account/infra_sptint1.git`
   2) В директории `/infra_sprint1`создайте файл .env
      Шаблон заполнения .env:
         SECRET_KEY
         DEBUG
         ALLOWED_HOSTS
   3) Установите менеджер пакетов и утилиту виртуальной среды ``` sudo apt install python3-pip python3-venv -y ```
   4) создайте виртуальное оеружение ``` python3 -m venv venv``` 
   5) активируйте виртуальное окружение ```source venv/bin/activate ``` 
   6) установите зависимости ```pip install -r requirements.txt ```
   7) выполните миграции ```python manage.py migrate```
   8) создайте супрепользователя ```python manage.py createsuperuser```
   9) запуск frontend
      ```curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash - &&\ sudo apt-get install -y nodejs```
      в директории ```<ваш проект>/frontend/``` выполнитe ```npm i```
   10) запуск gunicorn
       ```
       pip install gunicorn==20.1.0
       sudo systemctl start gunicorn
       sudo systemctl enable gunicorn
       ```
   11) запуск Nginx
       ```
       sudo apt install nginx -y 
       python sudo ufw allow 'Nginx Full'
       python sudo ufw allow OpenSSH
       python sudo ufw enable
       ```
   12) сбор статики
      в директории ```<имя_проекта>/frontend/``` выполнить ```npm run build```
      ```sudo systemctl reload nginx```

---
## Об авторе 
Автор проекта Яндекс.Практикум. 

Сборка: студентка Яндекс.Практикума Наталья Арлазарова
