# Cross-platform-avrdude-GUI
DaDuDa - простая кроссплатформенная графическая оболочка для avrdude, написанная на Qt.

Как оказалось, большинство графических оболочек для avrdude написаны для Windows, за исключением, разве что, "Burn-O-Mat". Но и он не захотел нормально работать на моей Orange Pi5 (запускался, но ничего не выполнял). А так как я не сторонник прописывать километры комманд в терминале, решил написать свою графическую оболочку.
Писать решил на Qt, так как для Linux я больше не знаком с другими способами создавать графические приложения (я не программист, и с Qt тоже знаком поверхностно, так что мой код получился даже на мой взгляд ужасным).
К тому же Qt является кроссплатформенной, поэтому моя оболочка может быть скомпилирована под многие ОС. 
Оболочка получилась очень минималистичной, интуитивно понятной. Скорее всего, могут быть ошибки, так как не реализована "защита от дурака". Проверялась толко с usbasp и stk500v1 на Windows x64, Linux (Fedora) x64, Linux (Ubuntu) aarch64. Для всех этих ОС есть скомпилированные бинарники.
Для Windows особого смысла использовать эту оболочку нет, так как есть множество других более навороченных, а вот на Linux, если Вы не сторонних мазохизма с консолью - может пригодиться.

![screenshot](https://github.com/AndrejChoo/Cross-platform-avrdude-GUI/blob/main/images/main_gui.png)

# Компиляция оболочки
Для сборки необходимо установить Qt-creator, обязательно установить qmake, QSerialPort. Открыть проект в Qt-creator очистить и скомпилировать с предварительно настроенными инструментами под свою архитектуру.

# Запуск программы
Для работы программы в:
Linux - необходимо установить avrdude

-Debian дистрибутивы: sudo apt install avrdude

-Arch дистрибутивы: sudo pacman -S avrdude

-RedHat дистрибутивы: sudo dnf install avrdude

Если невозможно открыть порт /dev/ttyUSB0, необходимо предоставить ему права доступа: sudo chmod a+rw /dev/ttyUSB0

Возможно, понадобятся некоторые Qt-шные пакеты, если Вы будете запускать готовые бинарники. Проверить можно при помощи запуска через консоль.

Windows - необходимо скопировать файлы "avrdude" и "avrdude.conf" в папку с программой; или в любое место, но тогда прописать путь в переменной Path.

# Поддержка
По возможности буду добавлять новые функции, оптимизировать код. Обратная связь приветствуется (andrejchukov@yandex.ru).
