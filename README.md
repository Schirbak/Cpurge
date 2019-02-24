# Cpurge

Плагин для Minecraft Bukkit. Помогает очищать карту от создаваемых игроками столбов.

### Принцип работы

Построенный игроком столб, превышающий максимальную высоту, автоматически разрушается через заданное количество времени. Игроку отправляется предупреждение о том, что он может отменить процесс, если кликнет по столбу ЛКМ.

### Конфигурация

Стандартная конфигурация:
```
messages:
  warning: "Построенный столб будет разрушен через минуту. Нажмите [ЛКМ] по столбу, чтобы отменить"
  postSaved: "Разрушение отменено"
  postRemoved: "Столб был разрушен"
settings:
  minHeight: 5
  removeTimeout: 60
  forgetTimeout: 300
  disableOnWorlds:
  - world1
```

Раздел `messages` отвечает за отправляемые игроку сообщения.
* Сообщение `messages.warning` отправляется игроку, при построении столба;
* `messages.postSaved` отправляется при клике по столбу для сохранения;
* `messages.postRemoved` отправляется при автоматическом разрушении столба.

Раздел `settings` отвечает за настройку плагина.
* `settings.minHeight` задаёт минимальную высоту столба, подлежащего удалению;
* `settings.removeTimeout` задаёт время, через которое столб удалится автоматически;
* `settings.forgetTimeout` задаёт время, через которое плагин перестаёт следить за столбом, высота которого меньше минимальной;
* `settings.disableOnWorlds` задаёт список миров, в которых плагин не будет работать.