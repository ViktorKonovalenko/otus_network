1. Теоретическая часть<br>
Высчитываем кол-во узлов<br>

| Name          | Сеть               | Маска  |  Кол-во адресов | Первый адрес в сети | Последний адрес в сети |  Broadcast — адрес |
| ------------- |--------------------| -----  | --------------- | ------------------- | -----------------------|--------------------|
|  || Central Network  |   |  | ||
| Directors     | 192.168.0.0/28 |   255.255.255.240 | 14 | 192.168.0.1 | 192.168.0.14	 | 192.168.0.15 |
| Office hardware     | 192.168.0.32/28 |   255.255.255.240 | 14 | 192.168.0.33 | 192.168.0.46	 | 192.168.0.47 |
| Wi-fi(mgt network)     | 192.168.0.64/26 |   255.255.255.192 |62 | 192.168.0.65 |192.168.0.126 | 192.168.0.127 |
|  ||Office 1 network |   |  | ||
| Dev     | 192.168.2.0/26 |   255.255.255.192 | 14 | 192.168.2.1 | 192.168.2.62 | 192.168.2.63 |
| Test     | 	192.168.2.64/26 |   255.255.255.192 | 14 | 192.168.2.65 | 192.168.2.126	 | 192.168.2.127 |
| Managers     | 192.168.2.128/26 |   255.255.255.192 | 14 | 192.168.2.129 | 192.168.2.190	 | 192.168.2.191 |
| Office hardware     |	192.168.2.192/26	 |  255.255.255.192 | 14 | 192.168.2.193  | 192.168.2.254 | 192.168.2.255 |
|  || Office 2 network  |   |  | ||
| Dev     |192.168.1.0/25  |   255.255.255.128 | 126 | 192.168.1.1 | 192.168.1.126 | 192.168.1.127 |
| Test     | 192.168.1.128/26 |   255.255.255.192 | 62 | 192.168.1.129 | 192.168.1.190 | 192.168.1.191 |
| Office     | 192.168.1.128/26|   255.255.255.192  | 62 | 192.168.1.193 | 192.168.1.254	 | 192.168.1.255 |
|  || InetRouter — CentralRouter network  |   |  | ||
| Inet — central     | 192.168.255.0/30 |  255.255.255.252 | 2 | 192.168.255.1 | 192.168.255.2	 | 192.168.255.3 |

Исходя из таблицы видим свободные сети:
- 192.168.0.16/28 
- 192.168.0.48/28
- 192.168.0.128/25
- 192.168.255.64/26
- 192.168.255.32/27
- 192.168.255.16/28
- 192.168.255.8/29  
- 192.168.255.4/30 


2. Практическая часть<br>
При выполнении ДЗ столкнулся с проблемой развертки всего стенда, не хватало ресурсов компьютера, пришлось сократить кол-во ВМ. Выполнял ДЗ на след ВМ(выделел красным).<br>
![image](https://github.com/ViktorKonovalenko/otus_network/assets/32430041/6630ff51-b8bd-485e-971b-43164f5c4a54)<br>
Однако Vagrantfile и ansible playbook были написан для всех ВМ, но не производилось его тестирование, если изначальный Vagrantfile не отработает, просьба запустить усеченный вариант. Название вагрантфайла: Vagrantfile2<br>
<br>
Запускаем Vagrant
<pre>vagrant up</pre>
Должен подняться след стенд и отработать ansible по настройке маршрутизации.<br>
![image](https://github.com/ViktorKonovalenko/otus_network/assets/32430041/fef26bc2-5236-4034-8f42-37a317c35844) <br>
Проверяем выход в интернет на сервере office1Server через traceroute.<br>
![image](https://github.com/ViktorKonovalenko/otus_network/assets/32430041/94bd9e6e-6f33-4da2-8ef6-53b295a1cfed) <br>
Видим что выход в интернет настроен через роутер inetRouter<br>
