# Manta. Гайд по установке и синхронизации.
## Установка Manta:

# Подготовка: 
### 1. Обновляем пакеты:
```shell  sudo apt update && sudo apt upgrade -y 
```

### 2. Устанавливаем инструменты разработчика и необходимые пакеты
```shell  sudo apt install pkg-config build-essential libssl-dev curl jq 
```

# Устанавливаем Rust:

### 1. устанавливаем необходимые пакеты:
```shell sudo apt install curl build-essential gcc make -y 
```

### 2. загружаем установочный скрипт Rust:
```shell curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh 
```

# Выбираем пункт 1) продолжить установку (по умолчанию).
<img src = https://img2.teletype.in/files/52/fd/52fda65d-6438-4d73-abc9-09d896c49b8c.png>

### активируем среду Rust для текущей оболочки
```shell source ~/.profile 
```

```shell source ~/.cargo/env 
``` 

# Установка ноды :
 
### 1. Клонируем репозиторий:
```shell git clone https://github.com/Manta-Network/manta-rs.git 
```

### 2. Переходим в папку с проектом и устанавливаем ноду:
```shell
cd manta-rs
cargo run --release --package manta-trusted-setup --all-features --bin groth16_phase2_client register
```

