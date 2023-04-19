---
## Front matter
title: "лабораторной работе n3"
subtitle: "markdown"
author: Джахангиров илгар Залид "

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: false # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы
    Научиться оформлять отчёты с помощью легковесного языка разметки Markdown
# Задание
 Сделайте отчёт по предыдущей лабораторной работе в формате Markdown.
– В качестве отчёта просьба предоставить отчёты в 3 форматах: pdf, docx и md (в архиве,
поскольку он должен содержать скриншоты, Makefile и т.д.)
    
# Теоретическое введение
Markdown — язык текстовой разметки, созданный писателем и блогером Джоном Грубером. Он предназначен для создания красиво оформленных текстов в обычных файлах формата TXT. Вам не нужны громоздкие процессоры вроде Word или Pages, чтобы создавать документы с жирным или курсивным начертанием, цитатами, ссылками и даже таблицами. Достаточно запомнить простые правила Markdown, и можно писать хоть в «Блокноте». Хотя специализированные Markdown-редакторы, конечно, намного удобнее.
Markdown — это облегченный язык разметки с синтаксисом форматирования обычного текста.
{Markdownbash,
 Справочные материалы по Markdown
https://learn.microsoft.com/ru-ru/contribute/markdown-reference,

# Выполнение лабораторной работы
Создали ключа ssh
Общая информация
    1. Алгоритмы шифрования ssh
        1. Аутентификация
В SSH поддерживается четыре алгоритма аутентификации по открытым ключам:
            ▪ DSA:
                • размер ключей DSA не может превышать 1024, его следует отключить;
            ▪ RSA:
                • следует создавать ключ большого размера: 4096 бит;
            ▪ ECDSA:
                • ECDSA завязан на технологиях NIST, его следует отключить;
            ▪ Ed25519:
                • используется пока не везде.
        2. Симметричные шифры
            ▪ Из 15 поддерживаемых в SSH алгоритмов симметричного шифрования, безопасными можно считать:
                • chacha20-poly1305;
                • aes*-ctr;
                • aes*-gcm.
            ▪ Шифры 3des-cbc и arcfour потенциально уязвимы в силу использования DES и RC4.
            ▪ Шифр cast128-cbc применяет слишком короткий размер блока (64 бит).
        3. Обмен ключами
            ▪ Применяемые в SSH методы обмена ключей DH (Diffie-Hellman) и ECDH (Elliptic Curve Diffie-Hellman) можно считать безопасными.
            ▪ Из 8 поддерживаемых в SSH протоколов обмена ключами вызывают подозрения три, основанные на рекомендациях NIST:
                • ecdh-sha2-nistp256;
                • ecdh-sha2-nistp384;
                • ecdh-sha2-nistp521.
            ▪ Не стоит использовать протоколы, основанные на SHA1.
    2. Файлы ssh-ключей
        ◦ По умолчанию пользовательские ssh-ключи сохраняются в каталоге ~/.ssh в домашнем каталоге пользователя.
        ◦ Убедил, что у меня ещё нет ключа.
        ◦ Файлы закрытых ключей имеют названия типа id_<алгоритм> (например, id_dsa, id_rsa).
            ▪ По умолчанию закрытые ключи имеют имена:
            ▪ id_dsa
            ▪ id_ecdsa
            ▪ id_ed25519
            ▪ id_rsa
        ◦ Открытые ключи имеют дополнительные расширения .pub.
            ▪ По умолчанию публичные ключи имеют имена:
            ▪ id_dsa.pub
            ▪ id_ecdsa.pub
            ▪ id_ed25519.pub
            ▪ id_rsa.pub
        ◦ При создании ключа команда попросит ввести любую ключевую фразу для более надёжной защиты вашего пароля. Можно пропустить этот этап, нажав Enter.
        ◦ Сменить пароль на ключ можно с помощью команды:
        ◦ ssh-keygen -p
Создали ключа ssh
    • Ключ ssh создаём командой:
    • ssh-keygen -t <алгоритм>
    • Создайте ключи:
        ◦ по алгоритму rsa с ключём размером 4096 бит:
        ◦ ssh-keygen -t rsa -b 4096
        ◦ по алгоритму ed25519:
        ◦ ssh-keygen -t ed25519
    • При создании ключа команда попросит ввести любую ключевую фразу для более надёжной защиты вашего пароля. Можно пропустить этот этап, нажав Enter.
    • Сменить пароль на ключ можно с помощью команды:
    • ssh-keygen -p
Добавили SSH-ключа в учётную запись GitHub
    • Скопируйте созданный SSH-ключ в буфер обмена командой:
    • xclip -i < ~/.ssh/id_ed25519.pub
    • Откройте настройки своего аккаунта на GitHub и перейдем в раздел SSH and GPC keys.
    • Нажмите кнопку ew SSH key.
    • Добавьте в поле Title название этого ключа, например, ed25519@hostname.
    • Вставьте из буфера обмена в поле Key ключ.
    • Нажмите кнопку Add SSH key.
Верификация коммитов с помощью PGP
    • Как настроить PGP-подпись коммитов с помощью gpg.
Общая информация
    • Коммиты имеют следующие свойства:
        ◦ author (автор) — контрибьютор, выполнивший работу (указывается для справки);
        ◦ committer (коммитер) — пользователь, который закоммитил изменения.
    • Эти свойства можно переопределить при совершении коммита.
    • Авторство коммита можно подделать.
    • В git есть функция подписи коммитов.
    • Для подписывания коммитов используется технология PGP (см. Работа с PGP).
    • Подпись коммита позволяет удостовериться в том, кто является коммитером. Авторство не проверяется.
Создали ключа
    • Генерируем ключ
    • gpg --full-generate-key
    • Из предложенных опций выбираем:
        ◦ тип RSA and RSA;
        ◦ размер 4096;
        ◦ выберите срок действия; значение по умолчанию — 0 (срок действия не истекает никогда).
    • GPG запросит личную информацию, которая сохранится в ключе:
        ◦ Имя (не менее 5 символов).
        ◦ Адрес электронной почты.
            ▪ При вводе email убедитесь, что он соответствует адресу, используемому на GitHub.
        ◦ Комментарий. Можно ввести что угодно или нажать клавишу ввода, чтобы оставить это поле пустым.
Экспорт ключа
    • Выводим список ключей и копируем отпечаток приватного ключа:
    • gpg --list-secret-keys --keyid-format LONG
    • Отпечаток ключа — это последовательность байтов, используемая для идентификации более длинного, по сравнению с самим отпечатком ключа.
    • Формат строки:
    • sec   Алгоритм/Отпечаток_ключа Дата_создания [Флаги] [Годен_до]
    •       ID_ключа
    • Экспортируем ключ в формате ASCII по его отпечатку:
    • gpg --armor --export <PGP Fingerprint>
Добавление PGP ключа в GitHub
    • Копируем ключ и добавляем его в настройках профиля на GitHub (или GitLab).
    • Cкопируйте ваш сгенерированный PGP ключ в буфер обмена:
    • gpg --armor --export <PGP Fingerprint> | xclip -sel clip
    • Перейдите в настройки GitHub (https://github.com/settings/keys), нажмите на кнопку New GPG key и вставьте полученный ключ в поле ввода.
    /home/izdzhakhangirov/Загрузки/photo1676739178(1).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739178.jpeg
/home/izdzhakhangirov/Загрузки/photo1676739179(7).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739179(6).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739179(5).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739179(4).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739179(3).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739179(2).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739191(5).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739191(4).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739191(3).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739191(2).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739191(1).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739191.jpeg
/home/izdzhakhangirov/Загрузки/photo1676739192(2).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739192(1).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739539(1).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739179(1).jpeg
/home/izdzhakhangirov/Загрузки/photo1676739179.jpeg
/home/izdzhakhangirov/Загрузки/photo1676739192.jpeg
/home/izdzhakhangirov/Загрузки/photo1676739539(2).jpeg



создание список литературы юдля этого скачал в папке  'bib'откроем фаил "cite.bib" и нем создаем по шаблону необходимо нам литературный источники
снимок екрана
/home/izdzhakhangirov/Изображения/Снимки экрана/Снимок экрана от 2023-02-25 05-56-10.png
/home/izdzhakhangirov/Изображения/Снимки экрана/Снимок экрана от 2023-02-25 06-23-49.png


# Выводы/

Я создал учотную запись устоновил програму .с генировал и устоновил програмный обиспечение дальнешим работать git hub
# Список литературы{.unnumbered}
1.
GNU Bash Manual [Электронный ресурс]. Free Software Foundation, 2016.
URL: https://www.gnu.org/software/bash/manual/.
2.
Newham C. Learning the bash Shell: Unix Shell Programming. O’Reilly Media,
2005. 354 с.
3.Zarrelli G. Mastering Bash. Packt Publishing, 2017. 502 с.
4.Robbins A. Bash Pocket Reference. O’Reilly Media, 2016. 156 с.
5.Таненбаум Э. Архитектура компьютера. 6-е изд. СПб.: Питер, 2013. 874 с.
6.Таненбаум Э., Бос Х. Современные операционные системы. 4-е изд. СПб.:
Питер, 2015. 1120 с.
::: {#refs}
:::
