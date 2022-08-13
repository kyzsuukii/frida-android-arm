## FRIDA ANDROID ARM
*its [FRIDA](https://github.com/frida/frida) for android with arm architecture*

normally you can install frida with `pip install frida-tools` (its will install frida and CLI) but if you do it on android with arm architecture then an error will occur because there is no frida available for android with arm architecture.

so its will help you to install frida in android with arm architecture.

## Requirement
* [Termux.](https://github.com/termux/termux-app)
* A rooted phone.

## Installing

* install python and tsu with command
```
$ pkg update && pkg upgrade -y
$ pkg install python tsu -y
```
* clone this repo
```
$ git clone https://github.com/kyzsuukii/frida-android-arm
$ cd frida-android-arm
```
* move `frida-15.2.2-py3.10-android-armv7l.egg` to `$HOME`
```
$ mv frida-15.2.2-py3.10-android-armv7l.egg $HOME 
```
or
```
$ mv frida-15.2.2-py3.10-android-armv7l.egg ~
```
* install frida and frida-tools
```
$ pip install frida==15.2.2 frida-tools==11.0.0 
```
* move frida-server to` $PREFIX/bin`
```
$ mv frida-server $PREFIX/bin
```

thats it.

## NOTE
u cant use frida without frida-server. u will got error like this
![](https://raw.githubusercontent.com/kyzsuukii/frida-android-arm/master/.img/issue.jpg)

so to use frida, `cd` to `/data/local/tmp` and run `frida-server` on on that directory
```
$ cd /data/local/tmp
$ sudo frida-server -C --listen=localhost:27082
```
![](https://raw.githubusercontent.com/kyzsuukii/frida-android-arm/master/.img/frida-server.jpg)

to connect `frida` and `frida-server`
```
$ sudo frida -H localhost:27042
```
![](https://raw.githubusercontent.com/kyzsuukii/frida-android-arm/master/.img/frida.jpg)

*now u can install objection, jnitrace or any program use frida in python*