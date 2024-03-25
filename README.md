Теоретическая часть<br>
Высчитываем кол-во узлов
| Name | Сеть	| Маска	| Кол-во адресов | Первый адрес в сети |	Последний адрес в сети |	Broadcast — адрес|
Вертикальные линии обозначают столбцы.

| Name          | Сеть               | Маска  |  Кол-во адресов | Первый адрес в сети | Последний адрес в сети |  Broadcast — адрес |
| ------------- |--------------------| -----  | --------------- | ------------------- | -----------------------|--------------------|
|  | Central Network  |         |
|: --------------------------------------------------------------------------------------------------------------------------------:|
| Directors     | 192.168.0.0/28 |   255.255.255.240 | 14 | 192.168.0.1 | 192.168.0.14	 | 192.168.0.15 |
| Office hardware     | 192.168.0.32/28 |   255.255.255.240 | 14 | 192.168.0.33 | 192.168.0.46	 | 192.168.0.47 |
| Wi-fi(mgt network)     | 192.168.0.64/26 |   255.255.255.192 |62 | 192.168.0.65 |192.168.0.126 | 192.168.0.127 |
| Directors     | 192.168.0.0/28 |   255.255.255.240 | 14 | 192.168.0.1 | 192.168.0.14	 | 192.168.0.15 |
| Dev     | 192.168.2.0/26 |   255.255.255.192 | 14 | 192.168.2.1 | 192.168.2.62 | 192.168.2.63 |
| Test     | 	192.168.2.64/26 |   255.255.255.192 | 14 | 192.168.2.65 | 192.168.2.126	 | 192.168.2.127 |
| Managers     | 192.168.2.128/26 |   255.255.255.192 | 14 | 192.168.2.129 | 192.168.2.190	 | 192.168.2.191 |
| Office hardware     |	192.168.2.192/26	 |  255.255.255.192 | 14 | 192.168.2.193  | 192.168.2.254 | 192.168.2.255 |
| Directors     | 192.168.0.0/28 |   255.255.255.240 | 14 | 192.168.0.1 | 192.168.0.14	 | 192.168.0.15 |
| Dev     |192.168.1.0/25  |   255.255.255.128 | 126 | 192.168.1.1 | 192.168.1.126 | 192.168.1.127 |
| Test     | 192.168.1.128/26 |   255.255.255.192 | 62 | 192.168.1.129 | 192.168.1.190 | 192.168.1.191 |
| Office     | 192.168.1.128/26|   255.255.255.240255.255.255.192  255.255.255.240 | 62 | 192.168.1.193 | 192.168.1.254	 | 192.168.1.255 |
| Office     |
| Inet — central     | 192.168.255.0/30 |  255.255.255.252 | 2 | 192.168.255.1 | 192.168.255.2	 | 192.168.255.3 |

Внешние вертикальные линии (|) не обязательны и нужны только, чтобы сам код Markdown выглядел красиво. Тот же код можно записать так:

Markdown | не такой | красивый
--- | --- | ---
*Но выводится* | `так же` | **клево**
1 | 2 | 3
