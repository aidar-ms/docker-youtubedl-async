Асинхронный экстрактор mp3 файлов из Youtube видео.

Программа принимает email адрес и youtube ссылку 
Проект использует supervisord для параллельного запуска gearmand сервера, gearman воркеров и php:7.2-apache образ. 

Для запуска проекта на своей машине нужно:

- Клонировать этот репозиторий на свой компьютер
- Задать данные своей БД в .env файле и в config/db.php
- Задать email адрес, для рассылки email в config/console.php. Ассоциативный ряд $config содержит поле ```'mailer' => [..., 'transport' => [ 'username' => '', 'password' => '' ], ...]```, в котором по умолчанию пустуют данные для username и password - их нужно заполнить учетными данными своего email адреса. Также по умолчанию smtp хост настроен на gmail: ```'host' => 'smtp.gmail.com'``` - его можно заменить на любой другой (smtp.mail.ru, smtp.yahoo.com, etc) Возможно, дополнительно придется сконфигурировать настройки своей email учетной записи, типа allow less secure apps на Gmail: https://support.google.com/accounts/answer/6010255?hl=en
- Запустить docker-compose up --build
- Должно работать :)