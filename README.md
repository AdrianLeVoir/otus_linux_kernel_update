# otus_linux_kernel_update

## Обновление ядра Linux (Ubuntu / mainline)

## 1. Проверка архитектуры и текущего ядра

```bash
uname -m && uname -r
```

## 2. Подготовка рабочей директории

```bash
mkdir ~/kernel && cd ~/kernel
```

## 3. Загрузка пакетов (пример для amd64)

```bash
wget https://kernel.ubuntu.com/mainline/v6.19.10/amd64/linux-headers-6.19.10-061910-generic_*.deb
wget https://kernel.ubuntu.com/mainline/v6.19.10/amd64/linux-headers-6.19.10-061910_*.deb
wget https://kernel.ubuntu.com/mainline/v6.19.10/amd64/linux-image-unsigned-6.19.10-061910-generic_*.deb
wget https://kernel.ubuntu.com/mainline/v6.19.10/amd64/linux-modules-6.19.10-061910-generic_*.deb
```
## 4. Установка

```bash
sudo dpkg -i *.deb
sudo update-grub
```
## 5. Перезагрузка и проверка

```bash
sudo reboot
uname -r  # после перезагрузки
```
