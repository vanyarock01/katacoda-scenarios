В данном терминале запущена ubuntu:18.04.
Устанавливать будем Tarantool 2.5 release.

## GPG-key

`curl https://download.tarantool.org/tarantool/release/2.5/gpgkey | sudo apt-key add -
`{{execute}}

## Кодовое имя ОС

Можно использовать утилиту lsb-release или задать вручную (в нашем случае bionic)
```sh
sudo apt-get -y install lsb-release
release=`lsb_release -c -s`
```
{{execute}}

## Репозитории
Добавим две строки в список репозиториев исходного кода
```sh
sudo rm -f /etc/apt/sources.list.d/*tarantool*.list
echo "deb https://download.tarantool.org/tarantool/release/2.5/ubuntu/ ${release} main" | sudo tee /etc/apt/sources.list.d/tarantool_2_5.list
echo "deb-src https://download.tarantool.org/tarantool/release/2.5/ubuntu/ ${release} main" | sudo tee -a /etc/apt/sources.list.d/tarantool_2_5.list
```
{{execute}}

## Установим тарантул

```sh
sudo apt-get -y update
```
{{execute}}

```sh
sudo apt-get -y install tarantool
```
{{execute}}

