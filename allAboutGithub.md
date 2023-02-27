# установка git

```bash
cd ~
```

```bash
sudo apt install apt-transport-https
```

```bash
sudo apt install git
```

```bash
sudo apt update && sudo apt upgrade
```

## тут можно качнуть GUI-версию Github-Desktop
[ссылка на реп - выбираем .deb](https://github.com/shiftkey/desktop/releases)

# настройка конфига

```bash
git config --global user.name "5met4nka"
```

```bash
git config --global user.email pavilich99@mail.ru
```

```bash
git config --global init.defaultBranch main
```

# настроиваем SSH-ключи для доступа к Git

* генерим ключ, в конце указываем почту
```bash
ssh-keygen -t ed25519 -C "pavilich99@mail.ru"
```

* `Enter a file in which to save the key` >> жмем `Enter`

* запускаем ssh-агент

```bash
eval "$(ssh-agent -s)"
```

* добавляем ключ в ssh-агент

```bash
ssh-add ~/.ssh/id_ed25519
```

* выводим ключ в консоль и копируем его

cat ~/.ssh/id_ed25519.pub

* [переходим по ссылке и жмем "New SSH key"](https://github.com/settings/keys)

* вставляем скопированный ключ и обзываем его именем компа

* жмем `Add SSH key`

# работаем с Github

* клонирование удаленного репозитория с удаленного сервера

```bash
git clone <ssh-link>
```

* узнать текущий статус

```bash
git status
```

* фиксация изменений

    * отдельных файлов

```bash
git add text1.txt test2.txt
```

    * всех файлов

```bash
git add .
```

* делаем коммит

```bash
git commit -m 'your text'
```

* пушим это добро на сервер

```bash
git push
```

[индус рассказывает о защите веток](https://www.youtube.com/watch?v=rYwwz1b2Nss)