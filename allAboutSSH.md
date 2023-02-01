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

# настройка alias'ов - кличек

[ссылка на видос](https://www.youtube.com/watch?v=b7GJG4te0l4&list=PLAk6CfuV7hyqHyQVHZMQRihAfebXpxn2O&index=29)

[ссылка на видос](https://itsecforu.ru/2019/05/06/%F0%9F%90%A7-%D0%BA%D0%B0%D0%BA-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D1%82%D1%8C-%D0%B0%D0%BB%D0%B8%D0%B0%D1%81-ssh-%D0%B2-linux/)

формат  

`Host home-pc`  
`Hostname 192.168.1.XX`  
`User nikita`  
