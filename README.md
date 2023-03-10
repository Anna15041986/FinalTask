# Инструкция по работе с Git.

## Git. Основы.
* Git — это одна из реализаций распределённых систем контроля версий (VCS), имеющая как локальные, так и удалённые репозитории, которая позволяет отслеживать и фиксировать изменения в коде: вы можете восстановить код в случае сбоя или откатить до более ранних версий. А ещё это must-have инструмент для взаимодействия нескольких разработчиков на одном проекте.Технически - это набор консольных утилит, которые отслеживают и фиксируют изменения в файлах. Изначально Git был создан Линусом Торвальдсом при разработке ядра Linux. Однако инструмент так понравился разработчикам, что в последствии, он получил широкое распространение и его стали использовать в других проектах. С его помощью вы можете сравнивать, анализировать, редактировать, сливать изменения и возвращаться назад к последнему сохранению. Этот процесс называется контролем версий.

 ## Подготовка репозитория.
 * __*git init*__   - команда на создание нового репозитория (инициализация). После успешного прохождения данной команды в папке, которую вы решили отслеживать появиться скрытая папка ‘ .git ‘. При этом название существующего в папке файла окрасится в зелёный цвет, а на против файла появится буква *U -untracked*, что значит неотслеживаемый.

## Последовательность действий при создании коммита.
- После внесения информации в отслеживаемый файл, около его названия в терминале появится белая жирная точка - это напоминание, что информация требует сохранения, сохранение осуществляется через __CTRL+S__. После этого белая точка в терминале исчезнет, а около названия файла появится буква М, что означает модифицированный, изменённый *(modified)*.
- __*git add “название файла”*__ - команда, которая добавляет файлу версионность в локальном репозитории  Git. После этого напротив названия файла появляется буква А.

- ### *Проверка состояния файла перед фиксацией.* 
  __*git status*__ — это еще одна важнейшая команда, которая показывает информацию о текущем состоянии репозитория: актуальна ли информация на нём, нет ли чего-то нового, что поменялось, и так далее.
- ### *Непосредственное создание commit:*
  __*git commit*__   - осуществляем фиксацию состояния файла командой __*git commit -m ”пояснение”*__. В пояснение кратко пишем суть вносимых изменений.

 ## Перемещения между сохранениями.

  * __*git checkout*__ - команда для премещения между коммитами, для этого правильно прописать её надо так - __*git checkout <номер коммита>*__

 ## Просмотр сохранённых commit.
* __*git log*__ - команда, с помощью которой можно вызвать для просмотра все фиксации отслеживаемого файла.
## Работа с ветками.
* Любая сложная работа, подразумевает подготовительную действия. Все подготовительные действия обычно располагают в черноики, а законченный результат называется чистовиком. Для выполнение аналогичных функций в гите предусмтрено создание ветвей. Ветвь - _branch_. Причём роль чистовика выполняет главная ветвь - master или main. А дополнительные ветви - это черновики. Ветви имеют свою собственную историю и изолированные друг от друга изменения до тех пор, пока вы не решаете слить изменения вместе. 
* **_git branch <название ветви>_** - команда по которой создаётся новая ветвь.

### Соединение черновика с чистовиком.
* **_git merge <название ветки>_** - комада выполняется в той ветке в которую будет добавлена (влита) второстепенная, то есть для слияние веток нужно находится в ветке **master**, чтобы влить черновую ветку.  
### Удаление отработанной ветви.
* После слияния  рабочей (черновик) ветки в исходную (чистовик) версию проекта, ее, по правилам хорошего тона, необходимо удалить, чтобы она более не мешалась в вашем коде. Но как это сделать?
Для локально расположенных веток существует команда: **_git branch -d <название ветки>_**.
Флажок -d являющийся опцией команды git branch - это сокращенная версия ключевого слова --delete, предназначенного для удаления ветки.

### Работа с тяжёлыми файлами.
*  Чтобы вставить изображение в текст, работая в разрешении md, достаточно написать следующее: ![Сармат](Sarmat.jpg). В квадратных скобках делается подпись, на случай если изображение не загрузится, а в круглых скобках указывается наименование файла. Но так как тяжёлые файлы не принято фиксировать в репозиториях В Git предусмотрена методика работы с такими файлами. Для этого в репозитории создаётся специальный файл **_.gitignore_**. Для этого необходимо проделать ряд действий:
* Создайте вручную файл под названием .gitignore и сохраните его в директорию проекта.
* Внутри файла перечислите названия файлов/папок, которые нужно игнорировать, каждый с новой строки.
* Файл .gitignore должен быть добавлен, закоммичен и отправлен на сервер, как любой другой файл в проекте.
##  Отслеживание изменений сделанных в commit.
Чтобы увидеть разницу между двумя коммитами, используется команда **_git diff_**. 
# GitHub. Коротко овзаимодействии.
## Удаленный репозиторий.
* Репозиторий, хранящийся в облаке, на стороннем сервисе (в нашем случае на GitHub), специально созданном для работы с git имеет ряд преимуществ:
 1.  Это своего рода резервная копия вашего проекта, предоставляющая возможность безболезненной работы в команде. 
 2. В таком репозитории можно пользоваться дополнительными возможностями хостинга
 * На GitHub можно создать удалённый репозиторий. Процесс создания репозитория интуитивно понятен. Чтобы иметь возможность работать непосредственно с репозиторием созданным в GitHub необходимо задать команду:
**_Git remote add origin адрес удалённого репозитория_** адрес копируется на странице  GitHub.
Для полной привязке к удалённому репозиторию необходимо выполнить ещё две команды:
* **_git branch -M main_**  - команда назначающая название главной ветви main
* **_git push -u origin main_**  - команда которая по сути и является повелительной, отправляющий локальный репозиторий в удалённый.
 ## Клонирование
**_git clone <адрес удалённого репозитория>_**  -  клонирование - это когда вы копируете удаленный репозиторий к себе на локальный ПК. Это то, с чего обычно начинается любой проект. При этом вы переносите себе все файлы и папки проекта, а также всю его историю с момента его создания. Чтобы склонировать проект, сперва, необходимо узнать где он расположен и скопировать ссылку на него.При клонировании в текущий каталог, там будет создана папка, в которую поместятся все проектные файлы и скрытая директория *__.git__*, с самим репозиторием, или с необходимой информацией о нем. В такой ситуации, для клонируемого репозитория, по умолчанию, будет создана папка с одноименным названием, но его можно залить и в другую директорию.
### Стягивание и слияние.
Когда в удалённом репозитории пояились новые коммиты и нам надо эти фиксации перенести в локальный репозиторий используется команда:
**_git pull_** - команда, которая по сути, стягивает и производит сляние коммитов и веток в локальном репозитории.

* для отправления новых коммитов из локального репозитория используется команда **_git push_** без сноски на адрес удалённого коммита.
## Что такое Git Fork?
Fork — это копия репозитория. Раздвоение репозитория позволяет свободно экспериментировать с изменениями, не затрагивая исходный проект.
Разветвление (Fork) в GitHub — это процесс создания копии полного репозитория для учетной записи пользователя на GitHub из другой учетной записи. Когда пользователь разветвляет репозиторий, все файлы в нем автоматически копируются в учетную запись пользователя на GitHub, и это выглядит как собственный репозиторий пользователя. Этот процесс похож на копирование папки с одного диска на другой диск компьютера. Затем пользователь может свободно использовать этот репозиторий либо для своих целей, либо экспериментировать с изменениями в коде. С помощью разветвления git пользователи могут разрабатывать свои собственные модификации кода, который принадлежит кому-то другому. Следует отметить, что этот процесс не оказывает никакого влияния на исходный код репозитория (также называемый восходящим репозиторием).
