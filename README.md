# mk_23_kr
## Курсовая работа по дисциплине "Микроконтроллеры мехатронных устройств"
## Автор работы: Колесников Святослав.
### Используемое ПО
1. arm-none-eabi-g++ --- кросс-компилятор.
1. make --- система сборки проекта.
1. cmake --- система управления проектом.
1. git --- система контроля версий.

#### Подсистема передачи телеметрического сигнала робота ассистента.

##### Используемые в проекте интерфейсы: SPI, JTAG, Ethernet.
1. SPI (англ. Serial Peripheral Interface, SPI bus — последовательный периферийный интерфейс, шина SPI) — последовательный синхронный стандарт передачи данных в режиме полного дуплекса, предназначенный для обеспечения простого и недорогого высокоскоростного сопряжения микроконтроллеров и периферии.

Простыми словами: предоставляет разъём для подключения устройств, использующих SPI, такие как датчики, память и другие периферийные устройства.
Предоставляет возможность подключения устройств, работающих через SPI интерфейс, к основному контроллеру (STM32F407) для обмена данными.

2. Интерфейс JTAG предназначен для подключения сложных цифровых микросхем или устройств уровня печатной платы к стандартной аппаратуре тестирования и отладки.
Компактный программатор JTAG в корпусе BH-20 обеспечивает возможность загрузки программного обеспечения и отладки на микроконтроллере STM32F407 и, возможно, других устройствах в схеме. 

На текущий момент интерфейс JTAG стал промышленным стандартом. Практически все сколько-нибудь сложные цифровые микросхемы оснащаются этим интерфейсом для:

    выходного контроля микросхем при производстве;
    тестирования собранных печатных плат;
    прошивки микросхем с памятью;
    отладочных работ при проектировании аппаратуры; 
    программного обеспечения.

3. Ethernet предоставляет интерфейс для связи с ПК через сетевое соединение.
Используется для обмена данными между микроконтроллером и компьютером посредством сетевого соединения.
Подключается с помощью LAN модуля (по стандарту).

##### Используемые внешние устройства для подключения к МК.

К микроконтроллеру STM32F407 подключаются несколько внешних устройств: сеть, DC-DC преобразователь (MP2307DN-LF-Z), технология Ethernet, модуль LAN, радиомодуль NRF24L01, программатор МК JTAG, модуль SPI. 

Сеть: в схеме используется компактный удобный разъём питания DG301_2, предназначенный для обеспечения удобства подачи питания в 12 вольт.
DC-DC преобразователь: используется MP2307DN-LF-Z и преобразует напряжение из 12 вольт в 3,3 вольта.
Технология Ethernet и модуль LAN: разъём для подключения сетевого кабеля и модуль локальной сети для передачи данных ПК.
Радиомодуль NRF24L01: беспроводной модуль связи, используемый для передачи данных в беспроводных сетях.

Радиомодуль обеспечивает беспроводную связь между устройствами в системе под управлением микроконтроллера. Имеет частоту 2.4 ГГц.
Данный модуль в схеме представлен в виде разъёма, т.к. все компоненты есть на самой плате модуля.
##### 
