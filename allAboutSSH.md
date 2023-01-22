# установка ssh

```bash
sudo apt-get install ssh
```

```bash
sudo apt install openssh-server
```

```bash
sudo apt install net-tools
```

```bash
sudo apt update && sudo apt upgrade
```

# турбо-команды

* создание пары публичный ключ-приватный ключ

```bash
ssh-keygen
```

* копирование публичного ключа на сервер

```bash
ssh-copy-id USER@IP
```

* подключение к серверу

```bash
ssh USER@IP
```

* скопировать ФАЙЛ (ПАПКУ) с КОМПА на СЕРВЕР

```bash
scp FULL_FILE_NAME_PC USER@IP:/FULL_DIRECTORY_NAME_SERVER
scp -r FULL_DIRECTORY_NAME_PC USER@IP:/FULL_DIRECTORY_NAME_SERVER
```

* скопировать ФАЙЛ (ПАПКУ) с СЕРВЕРА на КОМП

```bash
scp USER@IP:/FULL_FILE_NAME_NAME_SERVER FULL_DIRECTORY_PC
scp -r USER@IP:/FULL_DIRECTORY_NAME_SERVER FULL_DIRECTORY_NAME_PC
```
