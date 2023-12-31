# infra_sprint1

## Описание проекта 

Социальная сеть с возможностью выкладывать фото котиков и описывать их достижения.

## Стек 

Python 3.9, Docker, Nginx, PostgreSQL, Gunicorn, GitHub Actions

## Запуcк проекта: 

   1) скопировать проект с github  `git clone git@github.com:Your_account/infra_sptint1.git`
   2) В директории `/infra_sprint1/backend/kittygram_backend` создайте файл .env
      Шаблон заполнения .env:
         SECRET_KEY
         DEBUG
         ALLOWED_HOSTS
   3) Установите менеджер пакетов и утилиту виртуальной среды `sudo apt install python3-pip python3-venv -y `
   4) создайте виртуальное окружение `python3 -m venv venv`
   5) активируйте виртуальное окружение `source venv/bin/activate `
   6) установите зависимости `pip install -r requirements.txt `
   7) выполните миграции `python manage.py migrate`
   8) создайте суперпользователя `python manage.py createsuperuser`
   9) запуск frontend
      `curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash - &&\ sudo apt-get install -y nodejs`
      в директории `infra_sprint1/frontend/` выполнитe `npm i`
      
   10) gunicorn
       скопируйте файл `sudo cp -f infra/gunicorn_kittygram.service /etc/systemd/system/`
       запуск `sudo systemctl start gunicorn`
       автозапуск `sudo systemctl enable gunicorn`
       
   12) Nginx
       установка `sudo apt install nginx -y `
       запуск `sudo systemctl start nginx`
       скопируйте файл конфигураций `sudo cp -f infra/default /etc/nginx/sites-enabled/`
      
   13) сбор статики
      в директории `<имя_проекта>/frontend/` выполнить `npm run build`

   14) настройка Nginx
       копируем статику в другую папку `sudo cp -r /home/yc-user/infra_sptint1/frontend/build/. /var/www/kittygram/`
       перезапускаем nginx `sudo systemctl reload nginx`

## Об авторе 
Автор проекта Яндекс.Практикум. 

Сборка: студентка Яндекс.Практикума Наталья Арлазарова
