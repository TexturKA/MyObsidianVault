fancy sys info
```bash
neofetch
```
fancy version of top \ htop
```bash
btop
```

```bash
fish_config
```
Количество файлов в директории
```bash
ls | wc -l
```
История всех команд, где n - количество последних
```bash
history n
```
Имя хоста
```bash
hostmane
```
Версия ядра Linux
```bash
uname -r
```
Версия оболочки
```bash
bash --version
```
Что за система
```bash
cat /etc/os-release
```
```bash
cat system-release
```
Кто вошел в систему
```bash
who
```
Текущее время
```bash
date
```
Затраченное время на выполнение
```bash
time
```
Описание команды
```bash
whatis
```
Мануал по команде
```bash
man
```
Тип файла
```bash
file
```
Подсчет количества в файле l - строк m - символов w - слов (`ls /директория/` | `wcbash -l`)
```bash
wc
```
Удалить не пустую директорию
```bash
rm -rf
```
Перестраховаться и спросить что удаляешь
```bash
rm -i
```
Первые строки файла
```bash
head
```
Последние строки файла
```bash
tail
```
Сортировка строк в алфавитном порядке, `sort music.txt |uniq` - уникальные строки
```bash
sort
```
Файловая иерархия
```bash
man hier
```
Узнать встроенная или внешняя для bash
```bash
type
``` 
Бинарный поиск файлов
```bash
which
```
Утилита для поиска файлов
```bash
find
```
Поиск по индексам в системе - `updatedb`
```bash
locate
```
Создание псевдонимов команд
```bash
alias c='clear'
```
Удаление алиаса
```bash
unalias
```
Установить переменную окружения
```bash
var=x
```
Вывести переменную окружения
```bash
echo $var
```
Все переменные в том числе не дочерние, `env`  - дочерние
```bash
set | more
```
Удалить переменную окружения.
```bash
unset var
```
Уровень командной оболочки, 1 родительская, 2 и более дочерняя
```bash
echo $SHLVL
```
?
```bash
su
```
```bash
set
```
`gunzip` - архиватор
```bash
gzip
```
`zmore` - просмотрщик архивированных текстов
```bash
zcat
```
`bunzip2` - улучшенный архиватор
```bash
bzip2
```
`bzmore` - просмотрщик
```bash
bzcat
```
Проверка чего либо
```bash
test
```
VIM
```vim
:set number
```
```vim
:se nu
```
```vim
:syntax on
```
Посмотреть какой процесс слушает порт
```bash
netstat -lntup | grep ":порт"
```
Internet speed
```bash
speedtest-cli
```
?
```bash
VSCode - editor.formatOnSave
~/.config/Code/User/settings.json
```
Cоздать и активировать виртуальное окружение
```bash
python3 -m venv env
source env/bin/activate
```
Обновить pip
```bash
python3 -m pip install --upgrade pip
```
Установить зависимости из файла requirements.txt:
```bash
pip install -r requirements.txt
```
Docker
```bash
docker-compose up -d --build
```
```bash
dobashcker build -t worker .  
```
```bash
docker build -t redash .  
```
Автоудаление неиспользуемых пакетов
```bash
sudo apt autoclean && sudo apt autoremove
```
Текущий IP в inet `xxx.xxx.xxx.xxx`
```bash
ifconfig
```
Мониторинг производительности
```bash
htop
```
Полный путь до файла
```bash
realpath filename
```
Генерация секретного пароля
```bash
openssl rand -hex 32
```
vim:
`r`- замена
`u.` - отмена повтор
`shift` + `g` - вниз документа

Bluetooth
```bash
sudo systemctl status bluetooth.service
sudo systemctl restart bluetooth.service
```

Установка tar
```bash
tar xaf Downloads/xxx.tar.zst
cd xxxNew Contact VPN
sudo ./install.sh
```
Поиск и копирование файлов за последние дни(`ctime`) или минуты(`cmin`), в данном примере с тестового сервера
```bash
ssh voip@10.254.6.251 -t 'find find_dir -ctime -4 -printf %P\0'| rsync --files-from=- --from0 voip@10.254.6.251:/find_dir destn_dir
```
Задействованные порты
```bash
netstat -tuln | grep LISTEN
```
Убить процесс на порту 5060
```bash
sudo netstat -lpn |grep :5060
```
```
_____________
udp        0      0 0.0.0.0:5060            0.0.0.0:*                           24216/CEFWebKit  
----------------------
```
```bash
kill -9 24216
```
Записывать образ на флешку
```bash
balenaEtcher
```
?
```bash
git stash save
```bash``
` "my_stash_name"`
``
```bash
git stash list
```
```bash
git stash apply stash^{/my_stash_name}
```