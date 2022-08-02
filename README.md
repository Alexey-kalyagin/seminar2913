# **Инструкция для работы с Git**

![Логотип](Git_icon.svg.jpg)

## Что такое Git

Git - это одна из реализаци распределённых систем контроля версий

## Подготовка репрезитория

Чтобы создать/инициализировать новый репозиторий, ножно ввести в терминале команду:
*      git init 

### **Создание коммитов**

Для создания коммита требуется:

1. Определить в какой файл он будет сохранен. Для этого вводится команда: 
*       git add
после ввода команды указывается имя файла (для упращения, можно набрать первые символы имени файла и нажать кнопку "Tab" на клавиатуре. Программа сама допишет название).

2. Нужно оставить описание коммита. Вводится команда:
*       git commit -m "комментарий"
Коментарий вводится в ковычках. Комментарий должен быть прост и понятен. Чтоб при прочтении было понятно, какие изменения были внесены.

3. Для упрощения задачи, а именно для объединения двух вышепреведённых команд в одну существует команда:
*       git commit -a

4. После введения изменений в поле текста, его (текст) требуется сохранить. Для этого используют комбинацию клавишь на клавиатуре:
*       Ctrl+S
### **Просмотр состояния коммита**

Для просмотра текущего состояния коммита существует команда:
*       git status

### **Перемещение по коммитам**

Для перемещения по коммитам нам потребуется сделать несколько манипуляций:
1. Нужно узнать какие коммиты у нас сохранены и какие "адреса" они имеют. Для этого вводим команду:
*       get log
в появившихся окнах будет указан "адрес" и название коммита. Для более удобной визуализации можно доработать команду и выглядеть она будет так:
*       get log --oneline

2. Затем копируем нужный нам адрес коммита и вставляем в продолжение команды перехода действующего на сохранённый коммит:
*       git checkout 'скопированный адрес'
В данной коменде "скопированный адрес" вводится без ковычек или других знаков препинания! Адрес может быть указан не полностью - достаочно нескольких первых символов.

3. Для возврата в последнюю сохраненную версию есть команда:
*       get checkout master

### **Просмотр изменений коммитов**

Для просмотра изменений существует команда 
*       git diff
при вводе этой команды, в окне терминала высветится разница между нынешним состоянием и состоянием последнего сохранения текста

Если немного усовершенствовать команду, можно узнать что изменилось между разными коммитами. Для этого нужно прописать после вышеупомянутой команды адреса интересующих нас коммитов. выглядеть это будет так:
*       git diff 'адрес первого коммита' 'адрес второго коммита'
в этой команде так же не ставятся знаки препинания в обозначениях "адресов" коммитов.

### P.s.: 
для выхода из различных меню терминала используют кнопку клавиатуры "**Q**"

### **Добавление рисунка в документ**

Для того чтобы добавить рисунок в наш документ требуется:
* Заведомо скаченный рисунок поместить в папку нашего git
* Ввести в текстовом редакторе
*       ![подпись](имя файла и его разрешение)
* Сохранить и закоммитить изменения

### **Доп команды**

Чтобы проигнорировать тот или иной файл, нужно

1. Создать новый файл

2. Присвоить ему имя   ***.gitignore***

3. Внести нежелательный файл в этот файл

4. Сохранить и закоммитить изменения

Всё. нежелательный файл помещён в "чёрный список". Больше он не буде появляться в комадной строке. 

## Ветвление

Ветки в Git используются для одновременной работы с тексом несколькими пользователями. Грубо говоря для создание неких "черновиков", без вреда для оригинального документа. Благодаря коммитам, всегда видно где было произведено изменение и всегда можно "откатить" к более подходящей версии.  

### **Просмотр сущствующих веток**

Для просмотра списка существующих веток нужно ввести команду
       
*       git branch

### **Создание новых веток**

Для создания новой ветки нужно ввести команду 
*       git branch <имя ветки>

### **Слияние веток**

Для того, чтобы влить ветку в текущую нужно:
* переключить в ту ветку, ***в которую*** нужно влить текст
* ввести команду слияния с именем той ветки ***из которой*** нужно влить текст 

*       git merge <имя ветки>

Если при перенесении информации происходит конфликт текста (не совпадает текст в строках), то программа предлагает четыре варианта на выбор:
* оставить исходный текст
* выбрать тот, что сливаем
* слить оба варианта и отредактировать их в ручную
* посмотреть изменения

***P.s.:*** Если сливание происходит без конфликтов, то информация сохраняется автоматически. Если же произошёл конфликт текста, то следует сохранить и закоммитеть изменения!

### **Удаление веток**

Для удалении ненужных веток используют команду

*       git branch -d <имя ветки>

### **Доп. опции**

Можно наглядно продемонстрировать ответвления коммитов, введя команду

*       git log --graph

И получить ещё более развёрнутый результат, введя команду 

*       git log --all --oneline --graph


### P.s.: Почаще проверяйте статус и не забывайте всё коммитеть)

## Работа с "удалёнными" репозиториями

Для работы с "удалёнными" репозиториями пользуются сервисом ***GITHUB***

### **Команды для работы с "удалённым" репозиторием**

*       Git clone <адрес скопированной ссылки в Github>

Git скопирует репозиторий из указанной ссылке к нам на компьютер.
При дальнейшем запросе статуса (*Git status*), Git будет выдавать ошибку. Так как мы находимся не в нашей корневой папке (к которой привязан Git). Для дальнейшей работы требуется -

### **Изменить папку**

*       cd <имя нужной папки>

### **Загрузка репозитория**

Для загрузки своего репозитория на cервис ***Github*** нужно:

1. Создать аккаунт на сайте ***Github.com***

2. В верхнем правом углу нажать "+", *creat repository*

3. В появившемся окне ввести имя репозитория (может быть любым). 

4. Создать репозиторий (зелёная кнопочка внизу).

Сервис предложит три действия:

* Создать новый репозиторий

* Загрузить уже существующий Вашего компьютера

* Импортировать код из другого места

При копировании из Вашего компьютера (второй вариант), можно скопировать строки из окошка подсказки на сайте в Ваш терминал.

P.s.: Строчки нужно копировать по одной! И вводить тоже по одной!!!

 ### *Команды ввода из Github в наш терминал при переносе репозитория из коипьютере на сайт* 

*       git remote add origin <адрес на удаленный репозиторий>

При вводе этой командымы указываем адрес на "удалённый" репозиторий. Git запоминает адрес, и будущие изменения он будет отправлять на этот адрес.

*       Git branch -m <main>

Эта команда указывает, какая ветка будет основной. Можно заменить на *master*, чтоб не создавалась дополнительная ветка

*       git push -u origin <main> 

Эта команда направляет на "удаленный" репозиторий нашу информацию

Ввод этих трёх команд нужен, чтобы "подружить" наш репозиторий с "удалённым". Когда же наш Git "подружится" с нашем нашем аккаунтом в *Github*, отправлять все изменения можно будет одной командой ***git push***

### **Работа в редакторе репозитория на сервисе *github***

Для просмотра файла нужно два раза щёлкнуть на него. Затем, для редактирования нужно щёлкнуть на флажёк "*карандаш*"

Для "стягивания" актуальной информации с удалённого сервиса (после редактирования на Github) пользуются командой 

*       git pull

Для работы с чужими репозиториями в верхнем правом углу сайта есть кнопка "*Fork*". Эта кнопка перетягивает репозиторий с чужого аккаунта в наш. Где мы уже сможем вносить в него изменения.
Затем, залив командой *git pull* информацию на сервис *git hub*, нам предлагается команда *Compair and pull request* (править и предложить). Нажав на неё мы можем дать имя нашей ветке и добавить к ней описание.

P.s.: Все изменения делаются на отдельно созданной ветке!!!

## End