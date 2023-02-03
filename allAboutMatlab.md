# установка wireguard

```bash
sudo apt install wireguard
```

# копируем .conf файл с флешки в папку wireguard

```bash
sudo cp vpn3360.conf /etc/wireguard
```

# подключаемся к серверу

```bash
sudo wg-quick up vpn3360
```

# смотрим статистику подключения

```bash
sudo wg show
```

# пингуем сервер

```bash
ping 195.22.153.41
```

# установка matlab

```bash
sudo ./install
```

* далее делаем все по инструкции из письма

# запуск matlab

* убеждаемся что wireguard работает командой

```bash
sudo wg show
```

* убедились? запускаем!

```bash
cd /usr/local/MATLAB/R2021a/bin
```

```bash
./matlab
```

* после работы не забываем оффнуть vpn командой

```bash
sudo wg-quick down vpn3360
```