## Обновление ядра Linux (Ubuntu / mainline)

## Цель:
научиться обновлять ядро в ОС Linux;

### Описание/Пошаговая инструкция выполнения домашнего задания:

**Задание**

>1. Запустите ВМ c Ubuntu.
>2. Обновите ядро ОС на новейшую стабильную версию из mainline-репозитория.
>3. Оформите отчет в README-файле в GitHub-репозитории.


> В рамках задания выполнено обновление ядра Ubuntu с версии 6.8.0-106 до 6.19.10 из mainline-репозитория.

---

## 1. Проверка архитектуры и текущего ядра

```bash
uname -m && uname -r
````

Результат:

```
x86_64
6.8.0-106-generic
```

---

## 2. Подготовка рабочей директории

```bash
mkdir ~/kernel && cd ~/kernel
```

---

## 3. Загрузка пакетов (amd64)

```bash
wget https://kernel.ubuntu.com/mainline/v6.19.10/amd64/linux-headers-6.19.10-061910-generic_*.deb
wget https://kernel.ubuntu.com/mainline/v6.19.10/amd64/linux-headers-6.19.10-061910_*.deb
wget https://kernel.ubuntu.com/mainline/v6.19.10/amd64/linux-image-unsigned-6.19.10-061910-generic_*.deb
wget https://kernel.ubuntu.com/mainline/v6.19.10/amd64/linux-modules-6.19.10-061910-generic_*.deb
```

---

## 4. Установка ядра

```bash
sudo dpkg -i *.deb
sudo update-grub
```

Ключевые моменты установки:

```
Setting up linux-image-unsigned-6.19.10-061910-generic
update-initramfs: Generating /boot/initrd.img-6.19.10-061910-generic

Found linux image: /boot/vmlinuz-6.19.10-061910-generic
Found linux image: /boot/vmlinuz-6.8.0-106-generic
```

Новое ядро установлено, старое сохранено

---

## 5. Перезагрузка и проверка

```bash
sudo reboot
uname -r
```

Результат после перезагрузки:
```
6.19.10-061910-generic
```

Также подтверждается при входе в систему:
```
Ubuntu 24.04.3 LTS (GNU/Linux 6.19.10-061910-generic x86_64)
```

---

---

## Полный лог выполнения

[Полный вывод всех команд (wiki.js, требуется регистрация)](https://wiki.levoirlab.su/ru/practice/otus_homework/kernel)
