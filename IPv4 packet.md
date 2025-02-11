
* Заголовок — это все кроме поля Data.
* Считаем, что контрольная сумма не нужна, так как пакет будет в любом случае инкапсулирован в [[Ethernet frame]].

![[ipv4_packet_2.png|500]] ![[ipv4_packet_3.png]]

### Ver

Версия протокола IP 4 или 6, однако IPv6 пакет отличается заголовком пакета, а не только полем версии.

### IHL

IP header length в 4-х байтовых словах (минимум 5). Нужен, потому что заголовок может быть переменной длины благодаря полю Options.

### DSCP

Differentiated Services Code Point — приоритезация пакета и вероятность насколько пакет можно отбрасывать (например, приоритет у видео и аудио контента, чтобы воспроизводить их без задержек).

### ECN

Explicit Congestion Notification — «Явное Уведомление о Перегруженности». Eсть ли проблема с перегрузкой (истощением сети) сети, нужно ли предпринимать меры по разгрузке.

### Total length

Общая длина IP пакета в байтах (данных + заголовка). Максимальный размер пакета = 65 кБ, что превышает размер максимального Ethernet frame.

### Ident

Идентификатор пакета после фрагментации. Показывает, к какому пакету относится пакет: пакеты с одним идентификатором являются фрагментами одного пакета.

### Flags

Используются при фрагментации. Все три флага указываются в заголовке, например для несегментированного пакета флаги будут выглядеть как: 0,0,0 или 0,1,0.

  * 0 — зарезервирован и пока не используется.
  * DF (don't fragment) — если пришёл пакет с таким флагом и не влезает, то отбрасывается. Большинство ОС отправляют трафик с поднятым флагом DF.
  * MF (more fragments) — если пакет не является последним фрагментом, то число не 0, если является последним пакетом, то 0.

### Fragment Offset 

Cмещение (длина) пакета относительно начала поля дата (заголовки не учитываются) в 8-ми байтовых словах.

![[PacketOffset.png]]

### Time to live 

TTL — кол-во L3 хопов, на которое пакет может быть передан. Когда достигает 0 отбрасывается.

### Protocol

Протокол, использованный на транспортном уровне.

### Header checksum 

Контрольная сумма заголовка.

### Options

Поле переменной длины, которая кратна 4 байтам.

[[Network layer]]
[[IPv4]]
[[IPv4 address]]
[[Data structure]]