[вся инфа была взята отсюда](https://www.youtube.com/watch?v=5Aql0V-ta8A&t=390s)

# настройка сервера

* переходим в директорию Wireguard

```bash
cd /etc/wireguard
```

* создаем пару приватный/публичный ключ сервера

```bash
wg keygen | tee /etc/wireguard/server_privatekey | wg pubkey | tee /etc/wireguard/server_publickey
```

* ограничиваем доступ к файлу

```bash
chmod 600 server_privatekey
```

* создаем конфиг-файл `wg0.conf`

```bash
touch wg0.conf
```
* пишем в него

[Interface]  
PrivateKey = <server_privatekey>  
Address = 10.0.0.1/24  
ListenPort = 51830  
PostUp = iptables -A FORWARD -i %i -j ACCEPT; iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE  
PostDown = iptables -D FORWARD -i %i -j ACCEPT; iptables -t nat -D POSTROUTING -o eth0 -j MASQUERADE  

* включаем ip-форвардинг на сервере

```bash
echo "net.ipv4.ip_forward=1" >> /etc/sysctl.conf
```

*  убеждаемся что все четко

```bash
sysctl -p
```

* активируем сервис

```bash
systemctl enable wg-quick@wg0.service
```

* запускаем сервис

```bash
systemctl start wg-quick@wg0.service
```

* проверяем сервис

```bash
systemctl status wg-quick@wg0.service
```

# добавляем клиента

* создаем пару приватный/публичный ключ клиента

```bash
wg keygen | tee /etc/wireguard/user1_privatekey | wg pubkey | tee /etc/wireguard/user1_publickey
```

* открываем `wg0.conf` и добавляем клиента

[Peer]  
PublicKey = <user_publickey>  
AllowedIPs = 10.0.0.2/32  

* после добавления клиента перезапускаем сервер

```bash
systemctl restart wg-quick@wg0.service
```

# на компе клиента

* создаем wg.conf в домашней директории

```bash
cd ~
```

```bash
touch wg.conf
```

* пишем в него

[Interface]  
PrivateKey = <client_privatekey>  
Address = 10.0.0.2/32  
DNS = 8.8.8.8  

[Peer]  
PublicKey = <server_publickey>  
Endpoint = <server-IP>:51830  
AllowedIPs = 0.0.0.0/0  
PersistentKeepalive = 20  