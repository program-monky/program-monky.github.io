---
title: 'Как исправить ошибку Error #2006: MySQL Server has gone away'
date: 2022-12-01 16:03:00 Z
permalink: "/error-2006-mysql-server-has-gone-away"
categories:
- useful
tags:
- phpmyadmin
- xampp
- mysql
description: 'Ошибка "Error #2006: MySQL Server has gone away" встречается достаточно
  часто. Возникает при попытке импорта базы данных большого объема. Что ее исправить...'
header: 'Решение ошибки "Error 2006: MySQL Server has gone away"'
layout: post
---

Сегодня пытался развернуть на локальном сервере XAMPP сайт на LMS Moodle и столкнулся с ошибкой **"Error #2006: MySQL Server has gone away"**. Расскажу как ее исправить и успешно импортировать большую базу данных в phpmyadmin.

## Как исправить ошибку #2006: MySQL Server has gone away в панели phpmyadmin

Итак,  если вы получили данную ошибку в XAMPP значит пытаетесь загрузить дамп базы данных больших размеров. Чтобы импорт прошел без появления этой ошибки необходимо изменить настройки в файле my.ini. Файл находится по адресу: 

> Ваш диск:\xampp\mysql\bin\my.ini

Откройте данный файл и с помощью поиска (Ctrl+F) найдите параметр **«max_allowed_packet»**. 

По умолчанию будет указано **max_allowed_packet = 1М**. Установите любое большее значение, например **max_allowed_packet = 512М**. 

После этого сохраните и перезапустите XAMPP.

Это может быть не все, что вам потребуется сделать, чтобы избавиться от ошибки "Error 2006: MySQL Server has gone away". Не забывайте про настройки в файлах php.ini и настройки в файле конфигурации phpmyadmin.

Спрашивайте в комментариях, если появятся вопросы.
