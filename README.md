# Репозиторий для **pull request**
* В своём аккаунте на GitHub создать копию репозитория **"AndreyBulgakov19
/SCV_Git_2412"** с помощью кнопки **"Fork"**.
---
* Клонировать копию репозитория на локальный компьютер.
---
* Создать новую ветку.
---
* Добавить файл с инструкцией в новую ветку.
---
* Дополнить инструкцию разделами по работе с удалёнными репозиториями, pull request.
---
* Зафиксировать изменения (коммиты).
---
* Отправить изменения на GitHub.
---
* На сайте GitHub выполнить **Pull request**.
---
---
---
# Работа с удаленными репозиториями 

## 1. Создать аккаунт на Github

Чтобы создать новый аккаунт на сайте откройте главную страницу GitHub и тут же сразу вы можете ввести данные для новой учетной записи. Вам нужно указать имя пользователя, Email и пароль: Когда завершите ввод, нажмите кнопку “Sign Up Free. Никакая настройка github не нужна, достаточно лишь несколько кликов мышкой. На следующем шаге вам нужно выбрать тип репозитория. Для open-souce проектов использование сайта бесплатно. При необходимости иметь приватные репозитории, есть возможность перейти на платный тарифный план: Аккаунт готов, и вы будете перенаправлены на страницу, где сможете создать свой первый проект. Но перед тем как вы сможете это сделать, нужно подтвердить свой Email адрес.

---

## 2. Создать локальный репозиторий

Создание репозитория из существующего кода. git init Используйте команду, чтобы создать репозиторий из существующей папки на компьютере. В командной строке перейдите в корневую папку, содержащую код, и выполните следующую команду:

> git init. , 

чтобы создать репозиторий. Затем добавьте все файлы в папку в первую фиксацию с помощью следующих команд: 

> git add --all. > git commit -m "Initial commit".

---

## 3. Создать удаленный репозиторий

После проверки локального репозитория следующим шагом является создание удаленного репозитория, к которому будет подключаться локальный.
Создать удаленный репозиторий легко.
Войдите в GitHub и воспользуйтесь мастером «Create a new repository».

---

## 4. Связать удаленный репозиторий с локальным

На следующем шаге свяжем ЛР с УР, чтобы код, хранящийся на вашем компьютере, можно было размещать на GitHub (или брать с него).
URL на ваш УР скопируйте, зайдя на github.com и выбрав протокол, который вы настроили для взаимодействия с GitHub в прошлой статье.

В итоге команда будет выглядеть так (используйте ссылку на свой репозиторий!):

> git remote add origin https://github.com/ichimax/startjava2.git

Разберем ее по частям:

- git — используется приложение 
- git remote — управляет удаленным репозиторием
- add — добавляет информацию об УР в ЛР
- origin — общепринятый псевдоним для URL УР

>https://github.com/ichimax/startjava2.git — ссылка на УР
Эту длинную команду можно трактовать так: Git, добавь к себе информацию о связи между УР github.com/ichimax/startjava2.git, которому я хочу дать псевдоним origin, с ЛР.
Проверим, что получилось, введя git remote -v:

- git remote -v

>origin  https://github.com/ichimax/startjava2.git (fetch)
origin  https://github.com/ichimax/startjava2.git (push)
Взаимосвязь установлена успешно: напротив псевдонима origin размещается ссылка на УР.

---
 
## 5. Добавить удаленный репозиторий к проекту

'''
git remote add <имя для репозитория> <url-адрес репозитория сети>
'''

---

## 6. Ветвление

Ветки используются для разработки функциональности, изолированной от остальной. Ветка master используется по умолчанию, когда вы создаете репозиторий. Используйте другие ветки для разработки и слияние в master, когда разработка завершена.

Создать новую ветку с названием "feature_x" и переключиться на неё можно командой
- git checkout -b feature_x
  
переключиться обратно на master
- git checkout master
  
удалить ветку
- git branch -d feature_x

ветка не будет доступна тем, кто пользуется с вами удаленным репозиторием, пока вы не отправите её туда
- git push origin <имя_ветки>

---

## 7. Метки

Рекомендуется использовать метки для закрепления момента выпуска версий. Это популярная практика, которая также используется в SVN. Создать новую метку с именем 1.0.0 можно, выполнив

- git tag 1.0.0 1b2e1d63ff
1b2e1d63ff 

это первые десять цифр уникального идентификатора (id), с которым будет связана метка. Чтобы посмотреть идентификаторы коммитов, выполните
- git log

Можно использовать меньшее количество символов в качестве идентификатора, с учетом того, что он является уникальным.

---

## 8. Замена локальных изменений

В случае, если вы сделали что-то не то, вы можете заменить локальные изменения, используя команду
- git checkout -- <имя_файла>

произойдет замена изменений в вашем рабочем каталоге, на то, что сейчас находится в HEAD. Изменения, уже внесенные в индекс, также как и новые файлы, будут сохранены.

Если же вы хотите удалить все ваши локальные изменения и коммиты, получите (fetch) последние изменения с сервера и укажите локальной ветке master на них вот так
- git fetch origin
- git reset --hard origin/master

---

## 9. Твики и удобные команды

встроенный в git графический интерфейс
- gitk

использовать цветной вывод в терминале

- git config color.ui true

выводить в логе коммит на одной строке

- git config format.pretty oneline
  
интерактивный способ добавления в индекс

- git add -i

---

## 10. Обновление и слияние

Обновить ваш локальный репозиторий можно командой

- git pull

которая заберет изменения из удаленного репозитория и проведет слияние с активной веткой.
Для того чтобы слить другую ветку с активной (например master), используйте команду

- git merge <имя_ветки>

В обоих случаях git пытается автоматически слить изменения. К сожалению, это не всегда возможно и результатом станет конфликт. Вы ответственны за разрешение возникших конфликтов, путем ручного редактирования файлов, указанных git. После изменений вам надо пометить их как слитые

- git add <имя_файла>

перед слиянием вы можете предварительно посмотреть на изменения

- git diff <имя_ветки> <имя_другой_ветки>

---

## 11. Отправка изменений

Чтобы отправить эти изменения в ваш удаленный репозиторий, выполните

- git push origin master
- 
Можно изменить master на любую другую ветвь, чтобы отправить изменения на неё.

Если вы еще не клонировали существующий репозиторий и хотите подключить ваш к удаленному, вам нужно добавить его, выполнив

- git remote add origin <адрес_сервера>

Теперь вы можете отправлять изменения на удаленный репозиторий