# Manta. Гайд по установке и синхронизации.
## Установка Manta:
__________________________________________________________________________________________

# Подготовка: 
### 1. Обновляем пакеты:
```shell
sudo apt update && sudo apt upgrade -y 
```

### 2. Устанавливаем инструменты разработчика и необходимые пакеты
```shell
sudo apt install pkg-config build-essential libssl-dev curl jq 
```
__________________________________________________________________________________________

# Устанавливаем Rust:

### 1. устанавливаем необходимые пакеты:
```shell
sudo apt install curl build-essential gcc make -y 
```

### 2. загружаем установочный скрипт Rust:
```shell
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh 
```

# Выбираем пункт 1) продолжить установку (по умолчанию).
<img src = https://img2.teletype.in/files/52/fd/52fda65d-6438-4d73-abc9-09d896c49b8c.png>

### активируем среду Rust для текущей оболочки
```shell
source ~/.profile 
```

```shell
source ~/.cargo/env 
``` 
__________________________________________________________________________________________

# Установка ноды :
 
### 1. Клонируем репозиторий:
```shell
git clone https://github.com/Manta-Network/manta-rs.git 
```

### 2. Переходим в папку с проектом и устанавливаем ноду:
```shell
cd manta-rs
cargo run --release --package manta-trusted-setup --all-features --bin groth16_phase2_client register
```
## После завершения установки указываем свой твиттер и почту.

# На экран выведется информация с вашим публичным ключем, подписью и секретной фразой. 
<img src = https://img3.teletype.in/files/2c/33/2c338476-3f31-4f7e-baec-391b5214fae6.png>

## данные со всех "зеленых" строк вводим в форму :
https://mantanetwork.typeform.com/TrustedSetup
__________________________________________________________________________________________

### Создаем скрин (очередь сейчас занимает около 20 часов, если запустите без скрина, придется не выключать терминал все это время)
```shell
screen -S manta
```

### Переходим в папку и запускаем контрибуцию
```shell
cd manta-rs 
cargo run --release --package manta-trusted-setup --all-features --bin groth16_phase2_client contribute
```
### Вводим вашу секретную фразу (secret) и ожидаем своей очереди и участия в церемонии. 

### Если вывод показывает нечто похожее, больше ничего делать не нужно.
<img src = https://img4.teletype.in/files/f1/e5/f1e59355-fee6-49f2-8266-0513175bbe15.png>

### Выходим из скрина сочетанием клавиш Ctrl + A + D. По прошествии указанного времени заходим в скрин, чтобы убедиться что все прошло успешно.
```shell 
screen -x manta
```
