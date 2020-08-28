В данном терминале запущена ubuntu:18.04.
Устанавливать будем Tarantool 2.5 release.

## GPG-key

`curl https://download.tarantool.org/tarantool/release/2.5/gpgkey | sudo apt-key add -
`{{execute T1}}

## Кодовое имя ОС

Можно использовать утилиту lsb-release или задать вручную (в нашем случае bionic)
```sh
release=`lsb_release -c -s`
```{{execute T1}}

## Репозитории
Добавим две строки в список репозиториев исходного кода
```sh
sudo rm -f /etc/apt/sources.list.d/*tarantool*.list
echo "deb https://download.tarantool.org/tarantool/release/2.5/ubuntu/ ${release} main" | sudo tee /etc/apt/sources.list.d/tarantool_2_5.list
echo "deb-src https://download.tarantool.org/tarantool/release/2.5/ubuntu/ ${release} main" | sudo tee -a /etc/apt/sources.list.d/tarantool_2_5.list
```{{execute T1}}

## Установим тарантул

```sh
sudo apt-get -y update
```{{execute T1}}

```sh
sudo apt-get -y install tarantool
```{{execute T1}}
