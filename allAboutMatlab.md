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

## код активации

`32474-28142-05914-60484-57458-37776-16580-47076-14616-48594-15623-13148-48877-36021-38921-00044-19728-37494-53328-41493-54779-52330-56385-24036-36125`

## список рекомендуемых туллбоксов

* `MATLAB`
* `Similink`
* `Similink Control Design`
* `Comtrol System Toolbox`

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

# создадим скрипт запуска `matlab.sh`

```bash
cd /usr/local/MATLAB/R2021a
```

```bash
sudo gedit matlab.sh
```

* заполняем файл

```bash
#!/usr/bin/env bash

sudo wg-quick up vpn3360
cd /usr/local/MATLAB/R2021a/bin
./matlab
sudo wg-quick down vpn3360
```

* не забываем сделать его исполняемым

```bash
sudo chmod +x matlab.sh
```

# создадим ярлык

```bash
cd /usr/share/applications/
```

```bash
sudo gedit matlab.desktop
```

* заполним файл

```bash
[Desktop Entry]
Name=Matlab
Comment=
GenericName=
Keywords=matlab
Exec=sh /usr/local/MATLAB/R2021a/matlab.sh
Terminal=true
Type=Application
Icon=/usr/local/MATLAB/R2021a/534px-Matlab_Logo.png
Path=
Categories=
NoDisplay=false
```

* качаем логотип для отображения

```bash
cd /usr/local/MATLAB/R2021a
```

```bash
sudo wget https://upload.wikimedia.org/wikipedia/commons/thumb/2/21/Matlab_Logo.png/534px-Matlab_Logo.png
```

* готово! перезагружаем комп и наблюдаем иконку в меню