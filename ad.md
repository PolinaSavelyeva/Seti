---
aliases:
  - Administrative distance
description: Показывает насколько можно доверять конкретному источнику информации.
tags:
  - hot
---

### Для чего

Может случиться так, что в таблице маршрутизации есть записи с одинаковыми адресами и одинаковыми масками второй колонки (если бы маски были разными мы бы отдали предпочтение адресу с более длинной маской см. [[Как происходит маршрутизация]]). В таком случае предпочтение отдаётся той записи, в которой значение первого столбца имеет меньший AD. 

Например, маршруты построенные с помощью протокола [[OSPF]] предпочтительнее, чем построенные по протоколу [[RIP]]. А напрямую подключённые к [[Router|роутеру]] сети имеют максимальный приоритет. 

![[Excalidraw/AD.png]]

### Большая разница между OSPF и RIP

Она нужна для того, чтобы можно было вставить новые источники записей между.

[[RIB]]
