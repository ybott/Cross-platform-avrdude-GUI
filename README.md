# Cross-platform-avrdude-GUI
[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/jonatasemidio/multilanguage-readme-pattern/blob/master/README.md)
[![ru](https://img.shields.io/badge/lang-ru-blue.svg)](https://github.com/jonatasemidio/multilanguage-readme-pattern/blob/master/README.ru.md)

# Cross-platform-avrdude-GUI
DaDuDa is a simple cross-platform graphical front-end for avrdude, written in Qt.

As it turns out, most of the graphical shells for avrdude are written for Windows, with the possible exception of "Burn-O-Mat". But it didn’t want to work normally on my Orange Pi5 (it started, but didn’t do anything). And since I’m not a fan of writing kilometers of commands in the terminal, I decided to write my own graphical shell.
I decided to write in Qt, since for Linux I am no longer familiar with other ways to create graphical applications (I am not a programmer, and I am also only superficially familiar with Qt, so my code turned out terrible, even in my opinion).
In addition, Qt is cross-platform, so my shell can be compiled for many operating systems.
The shell turned out to be very minimalistic and intuitive. Most likely, there may be errors, since “fool protection” is not implemented. Tested only with usbasp, flip1 and stk500v1 on Windows x64, Linux (Fedora) x64, Linux (Ubuntu) aarch64. There are compiled binaries for all these OSes.
For Windows there is no particular point in using this shell, since there are many other more sophisticated ones, but on Linux, if you are not a third-party masochist with the console, it can come in handy.

![screenshot](https://github.com/AndrejChoo/Cross-platform-avrdude-GUI/blob/main/images/main_gui.png)

# Compiling the shell
To build, you need to install Qt-creator, be sure to install qmake, QSerialPort. Open the project in Qt-creator, clean it and compile it with pre-configured tools for your architecture.

# Running the program
To run the program in:
Linux - need to install avrdude

-Debian distributions: sudo apt install avrdude

-Arch distributions: sudo pacman -S avrdude

-RedHat distributions: sudo dnf install avrdude

You also need to install two packages: qt6-base-dev and libqt6-serialport-dev.

If port /dev/ttyUSB0 cannot be opened, you need to grant it permissions: sudo chmod a+rw /dev/ttyUSB0

Windows - you need to copy the files "avrdude" and "avrdude.conf" to the folder with the program; or to any place, but then write the path in the Path variable.

# Support
If possible, I will add new functions and optimize the code. Feedback is welcome (andrejchukov@yandex.ru).
