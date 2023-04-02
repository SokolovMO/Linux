# создаем конфиг-файл

```bash
touch ~/.tmux.conf
```

# назначаем комбинацию CTRL + q как командную

```bash
echo "set-option -g prefix C-q" >> ~/.tmux.conf
```

# делаем возможным масштабировать терминалы мышкой

```bash
echo "set -g mouse on" >> ~/.tmux.conf
```

[мужик объясняет базу](https://www.youtube.com/watch?v=1Y2CD4WnbP0)  

[первый сайтик со шпаргалкой](https://habr.com/ru/post/327630/)  

[второй сайтик со шпаргалкой](https://1cloud.ru/help/linux/tmux_help)  

[третий сайтик со шпаргалкой](https://losst.pro/shpargalka-po-tmux#:~:text=%D0%9A%D1%80%D0%BE%D0%BC%D0%B5%20%D1%82%D0%BE%D0%B3%D0%BE%2C%20%D0%B2%20tmux%20%D0%B5%D1%81%D1%82%D1%8C,%D0%BC%D0%BE%D0%B6%D0%BD%D0%BE%20%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D1%8C%20%D1%82%D0%B0%D0%BA%D0%B6%D0%B5%20%D0%B4%D0%BB%D1%8F%20%D0%BF%D1%80%D0%BE%D0%BA%D1%80%D1%83%D1%82%D0%BA%D0%B8.)  

запуск новой сессии под названием "first"

```bash
tmux new-session -s first
```

подключение к сессии под названием "first"

```bash
tmux attach -t first
```

управление происходит сочетаниями клавиш CTRL + b(по умолчанию) + команда  

* Shift + 5 - деление онка пополам по вертикали

* Shift + э - деление онка пополам по горизонтали
