# Работа с Github

Перед началом работы делаем резервную копию проекта. 
Если вы уже начали работать с гитом, но что-то не получается, лучше начать с начала.

Инструкция проверена от начала и до конца и если в точности следовать тому, что здесь написано, у вас все получится.

Предварительно рекомендую ознакомиться с материалами по работе с github в личном кабинете.

## 1. Клонирование репозитория наставнка и создание своего

#### Данный пункт выполняем, если решили делать работу с gulp сборкой, если не используете gulp можете сразу переходить у пункту 1.1

Копируем адрес репозитория тип соединения не важен т.к. к моему репозиторию у вас доступа не будет. Но для своего репозитория о том как его настроить можете посмотреть тут https://youtu.be/MnU1U7GCWLk

Ссылка на репозиторий с gulp сборкой https://github.com/blckbrrynvdr/WebMiddleGulp

![Alt text](https://downloader.disk.yandex.ru/preview/e04b54c46a10c68d0b9d0ea5b70c45b238751d1f18ea20b776f9b35ee6468d10/5cc99daf/1RO3FSj1zOa5MD1aEd1ndxqw6Vc-cZ-qgGC3H97yu_hg6j8pHjflIwDkB94jBgP2UznN3TIB4_ySdeCWsDYPkw%3D%3D?uid=0&filename=1.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&tknv=v2&size=2048x2048)

Открываем терминал и заходим в папку с проектом

Пишем (если хотим склонировать проект со сборкой):
```{r, engine='bash', count_lines}
git clone https://github.com/blckbrrynvdr/WebMiddleGulp.git burger
```
Псоледнее слово (burger) можете заменить на choco или любое другое, это будет название папки, в которую склонируется проект.

После чего в папке, где вы сделали эту команду должны появиться папка со сборкой проекта

![Alt text](https://downloader.disk.yandex.ru/preview/7756d2168b77fe56313d10d7b13dff2d2e15480d2f0879bf0dbb6f1515e80a09/5cc9aed8/Tz4DGIfOqdhg2K4Uq5SUYmcFOXWTRmJq6rcuz4NSwHK_OhoG_dSElF33v7FGVGL1KGPALc8VKeaN1W2Cy-Dlyg%3D%3D?uid=0&filename=22.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&tknv=v2&size=2048x2048)


### 1.1 Создаем свой удаленный репозиторий

Создаем новый репозиторий на github

![Alt text](https://downloader.disk.yandex.ru/preview/b5968911a11160f8f8d539ee013b1d2a636097cace18b2ec14890f5b27d133ec/5cc99d73/JM_omLnXkHCqUIFLSABuZ0v-0QJwiITuGs-w8pb9b_1sKrJ8cDcoG5BDB9iQTZUpb4ahm_U0eEaM-t3fyACThQ%3D%3D?uid=0&filename=2.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&tknv=v2&size=1920x937)

## 2. Работа с репозиторием на компьютере

### 2.1 Создаем связь с личным удаленным репозиторием
Открываем терминал и заходим в папку с проектом (папка в которой есть папка .git)

![Alt text](https://downloader.disk.yandex.ru/preview/319c6a4e1f2fa6a8320c5a07ffa7a65b938a527c3d72cf75e6c6a7776b8a2c78/5cc9a53c/JG5ha30Bu-LmCX3O6tbpgM7Bv15XXQ9tZnyC8B_CDZkntgQqkuY1AyLYxZ7tTesrRPC2hrRLCYgED7_SrdTc3Q%3D%3D?uid=0&filename=3.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&tknv=v2&size=2048x2048)

Далее выполняем связь своего удаленного репозитория с этой папкой, но командой которая вам предлагается на gitHub этого не получится сделать, т.к. при клонировании репозитория вы автоматические локальный привязали к репозиторию наставника. Эту связь разрушаем командой
```{r, engine='bash', count_lines}
git remote set-url origin https://github.com/blckbrrynvdr/WebMiddleGulp.git
```
Где https://github.com/blckbrrynvdr/WebMiddleGulp.git - ваш репозиторий (подставьте сюда адрес вашего удаленного репозитория)

![Alt text](https://downloader.disk.yandex.ru/preview/67bdc78f9248056ef9d67a9c8101a1bed8628e2f62dd1b93c0e28a59d2f9133b/5cc9af80/LVUaP6cXYtY55MhnSInr5wvpM6tl-bCuBtD1k9m4JwYsiZjeKCDyb-Kp-XRtTSuPPt4j8450LD4TjSsMccykXw%3D%3D?uid=0&filename=4.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&tknv=v2&size=2048x2048)

Если не клонировали мой репозиторий с gulp сборкой, то выполняем команду которая подсказывается при создании репозитория
```{r, engine='bash', count_lines}
git remote add origin https://github.com/blckbrrynvdr/WebMiddleGulp.git
```

После того как создали связь с личным репозиторием делаем команду
```{r, engine='bash', count_lines}
git push -u origin master
```
У Вас запросит название аккаунта и пароль (если не подключен ssh), после корректного ввода произойдет загрузка файлов в ваш удаленный репозиторий.

### 2.2 Создаем недельную ветку и начинаем разработку

Переходим в папку проекта и локально создаем новую ветку (напоминаю корнем вашего проекта будет папка в которой лежит папка .git, не путайтесь, если какие-то вопросы пишите мне в личку) 

```{r, engine='bash', count_lines}
git checkout -b week_1
```
![Alt text](https://downloader.disk.yandex.ru/preview/0e9b7589a1beadc7f7e1b65580370bb5b6a5489e5a0e7795643cffbc11385496/5cc9b040/409WVYDtMhG-0UN5At9zA6gmVm1Du8vPqQU4pxqbCFVaan5PIzWZWMV3ioPABqV6fKLoLJgV7g1P-QJuZXAX7A%3D%3D?uid=0&filename=5.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&tknv=v2&size=2048x2048)

Работаем в этой ветке (вставляем файлы из сохраненной папки в сборку то, что вы уже сверстали или сделали или пишем с нуля если ничего не делали)

Изменяем readme.md файл используя MARKDOWN разметку: указываем в нем
* Свое ФИО
* Имя наставника
* Название курса

![Alt text](https://portomebel.ru/upload/loft/7.png)

После делаем, только всегда смотрите в какой ветке вы находитесь в данном случае мы пока в week_1

```{r, engine='bash', count_lines}
git add .
git commit -m "Текст коммита"
```

![Alt text](https://downloader.disk.yandex.ru/preview/8a2d93db11c29eec2f6747eeb1f8fc8e97d511537e899ba9590aea1c64772890/5cc9b0ea/mMpD5WCD_ps_ajxHT80hYrtCOY9YRwiJBhfYCQysAS63aF6Y_llf6INRaXNqg2uqxk_TJKD2vwy8XlKxf65MvA%3D%3D?uid=0&filename=6.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&tknv=v2&size=958x927)

Коммит создан

Делаем push изменений в удаленный репозиторий (ВНИМАТЕЛЬНО мы делаем пуш уже не в ветку MASTER, а в ветку week_1 она автоматически создаться в вашем личном удаленном репозитории если ее там нет)

```{r, engine='bash', count_lines}
git push -u origin week_1
```

![Alt text](https://downloader.disk.yandex.ru/preview/1c405d0c01fc709ea1222d0bde198644d43896f83891e842a25e76fb63a93526/5cc9b143/PHG-5FVS-TCm9xtwI1gwVBTF8lqOaiAbeqxS_PBHWUd8z7LABe5OtzY24C6_k87eXz6_N-ZQyrMz1CIfDAKZhg%3D%3D?uid=0&filename=7.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&tknv=v2&size=2048x2048)

## 3. Проверка работы и сдача работы наставнику

Для того чтобы показать работу настанику ее необходимо отобразить либо на хостинге, либо на Github Pages. Второй вариант предпочтительнее.

Создаем новую ветку (ВАЖНО ветку создаем на удаленном репозитории и находиться нужно на ветке week_1) на github называем ее gh-pages

![Alt text](https://portomebel.ru/upload/loft/10.png)
![Alt text](https://portomebel.ru/upload/loft/11.png)

Заходим с настройки репозитория 
1. Переходим на вкладку settings
2. Выбираем ветку gh-pages. Нажимаем save

![Alt text](https://downloader.disk.yandex.ru/preview/fa111df4e8d91f33209c612b21fbcb52a30ff1e12783204f3f221639f9eb70ff/5cc9b206/bnQVsdvfaHWtt-QNje1SjoHVbkARdWD_T9DefsGgB2W35DWUvJJvSFDo32VuQPjfOUEk2kfz5HtVyh_v56ML6w%3D%3D?uid=0&filename=8.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&tknv=v2&size=2048x2048)

Создаем pull request из week_1 в master
![Alt text](https://downloader.disk.yandex.ru/preview/e1336cf4df1a1ce1690ea11bb4d78df4ef3de22ceae6e6636a0268a531596f49/5cc9b2d6/sYlhvLX46GVnogDbJcn88tyZL-SMeD4874k4In6t20iHfjd0GBbSN47dqjhnSBaC_nakwQ3kay7WzEDk7Cfv6w%3D%3D?uid=0&filename=9.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&tknv=v2&size=2048x2048)
![Alt text](https://downloader.disk.yandex.ru/preview/6f0d5c7fe0bf5b8b20f7b2a27f18e5f1487773a601d48327e5fdd4cc76580475/5cc9b377/iigDum-mF3BOMpe9zm8p5L26fwkEY6YrPpmGgAfim277v9uatHUd8pKHOVecTaPCcUJzXA0ssWRnxd5Toh6Qpw%3D%3D?uid=0&filename=10.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&tknv=v2&size=2048x2048)

### Публикуем изменения на github pages ###

После того как мы поработали локально в недельной ветке, т.е. например вы что-то доработали или исправили и хотите сдать мне на проверку в консоли пишем 

(Это если у вас локально что-то изменилось)
```{r, engine='bash', count_lines}
git push origin week_1
```
Потом обновляем то что в ветке gh-pages на удаленном.
```{r, engine='bash', count_lines}
git push origin week_1
git push origin week_1:gh-pages
```
*week_1 заменяем на текущую недельную ветку*. Таким образом все актуальные изменения мы заливаем на gh-pages и они будут доступны по ссылке которую вы пришлете наставнику.

![Alt text](https://downloader.disk.yandex.ru/preview/3e8fb1896a3bf8e81d429f3f6c2cbc3e81d09d04be44e0a6bc83a5b20222fe35/5cc9b3bf/YsCWAgNr1W_327IaE0lq4Na2XN4nQNm8EiUvK4ev8W-msZrKsbFCPI8PMqRpMzXQLyl0YIdaFP694LS3nnazlw%3D%3D?uid=0&filename=11.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&tknv=v2&size=1133x927)

На гите появится вот такая запись 

![Alt text](https://downloader.disk.yandex.ru/preview/842ae2e18c3109b21960bd6bad973d391ef6984826cfb2af25e46fe59af3c9f2/5cc9b454/Ti3u4UAJZ1nj8oFb4HTRU-EU2MUhcR5cxxzzUHX3-XVQfVxLBtJrGawxdjZom0J6tm65VunCzZ_oj1_Uu6Y4dA%3D%3D?uid=0&filename=12.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&tknv=v2&size=2048x2048)

### Добавляем настаника в collaborators ###
1. Открываем вкладку Settings
2. Переходим в раздел collaborators
3. Пишем ник настаника 
4. Жмем на кнопку

![Alt text](https://downloader.disk.yandex.ru/preview/3f4b8aa3da1117968133d9ffb39600992ada6b88ddc7bf1fc44191af51469cc8/5cc9b4db/DjycVjG8csSJEO7vBZCy_Xb3rBb4NES0gV41vPrAgx-As5K7LuogmeSGFerXr1psT4jHCzsELrilfi3HCA4uCQ%3D%3D?uid=0&filename=13.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&tknv=v2&size=2048x2048)

### Пишем наставнику, что все сделали, ждем ответа. ###

## 4. Доработка

Далее делаем доработки, коммитим их и пушим в туже ветку из которой создавали pull request.(не забываем сделать пуш в gh-pages ветку, чтобы изменения отобразились на gh-pages) 

**Новый pull request создавать не нужно** (вы и не сможете создать новый, пока я не закрыл старый), изменения подтянутся в прошлый. 

**Пишем наставнику, что все поправили, ждем ответа.**

## 5. Новые задания

После того как настаник примет задание вашей первой недели он смержит в мастер все изменения (это делаем именно наставник, т.е. **сами** пулреквест **не закрываем!**). 
Вы проверяете что находитесь на нужно(актуальной) ветке и из нее создаете новую ветку week_2 (или друю недельную ветку)
```{r, engine='bash', count_lines}
git checkout -b week_2
```
Работаете в новой ветке, делаете коммит и пуш на удаленный репозиторий 


Создаете новый pull request и снова пишите настанику

