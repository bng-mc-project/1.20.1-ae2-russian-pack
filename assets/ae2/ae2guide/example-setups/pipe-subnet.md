---
navigation:
  parent: example-setups/example-setups-index.md
  title: Предметная/Жидкостная кабельная подсеть
  icon: storage_bus
---

# Предметная/Жидкостная кабельная подсеть

Простой способ подражения предметного/жидкостного кабеля/трубы с помощью AE2 [устройств](../ae2-mechanics/devices.md), который можно использовать для любых целей, для которых обычно используются предметные/жидкостные кабели
Это включает в себя возвращение результата крафта в <ItemLink id="pattern_provider" />.

Как правило, для достижения этой цели существует два различных метода:

## Шина импорта -> Шина хранения

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_storage_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        (1) Шина импорта: может быть отфильтрована.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        (2) Шина хранения: может быть отфильтрована. Это (и другие шины хранения, которые вы хотите использовать в качестве пункта назначения)
        должно быть единственным хранилищем в сети.
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#00ff00">
        Источник
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#00ff00">
        Место назначения
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<ItemLink id="import_bus" /> (1) в инвентаре источника импортирует предметы или жидкость и пытается сохранить их в [сетевом хранилище](../ae2-mechanics/import-export-storage.md).
Поскольку единственным хранилищем в сети является <ItemLink id="storage_bus" /> (2) (поэтому это подсеть, а не ваша основная сеть), предметы или жидкость
размещаются в инвентаре места назначения, таким образом переносясь. Энергия поставляется через <ItemLink id="quartz_fiber" />.
Как шина импорта, так и шина хранения могут быть отфильтрованы, но при отсутствии фильтров установка будет передавать все, к чему она имеет доступ.
Эта установка также работает с несколькими шинами импорта и несколькими шинами хранения.

## Шина хранения -> Шина экспорта

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/storage_export_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        (1) Шина хранения: может быть отфильтрована. Эта (и другие шины хранения, которые вы хотите использовать в качестве источника)
        должно быть единственным хранилищем в сети.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        (2) Шина импорта: должна быть отфильтрована.
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#00ff00">
        Источник
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#00ff00">
        Место назначения
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<ItemLink id="export_bus" /> в инвентаре назначения пытается извлечь предметы из своего фильтра из [сетевого хранилища](../ae2-mechanics/import-export-storage.md).
Поскольку единственным хранилищем в сети является <ItemLink id="storage_bus" /> (поэтому это подсеть, а не ваша основная сеть), предметы или жидкость
извлекаются из инвентаря источника и таким образом передаются. Энергия поставляется через <ItemLink id="quartz_fiber" />.
Поскольку для работы шины эспорта должны быть отфильтрованы, эта установка работает только в том случае, если вы фильтруете шину экспорта.
Эта установка также работает с несколькими шинами хранения и несколькими шинами экспорта.

## Установка, которая не работает (Шина импорта -> Шина экспорта)

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_export_pipe.snbt" />

<BoxAnnotation color="#dd3333" min="3.7 0 0" max="4 1 1">
        Шина импорта: Поскольку сеть не имеет хранилища, ей некуда импортировать данные.
  </BoxAnnotation>

<BoxAnnotation color="#dd3333" min="1 0 0" max="1.3 1 1">
        (2) Шина экспорта: поскольку сеть не имеет хранилища, ей нечего экспортировать.
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#ff0000">
        Источник
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#ff0000">
        Место назначения
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Установка, состоящая только из шины импорта и экспорта, не будет работать. Шина импорта будет пытаться извлечь из инвентаря источника
и сохранить предметы или жидкость в сетевом хранилище. Шина экспорта будет пытаться извлечь из сетевого хранилища и поместить
предметы или жидкость в инвентарь назначения. Однако, поскольку эта сеть **не имеет хранилища**, шина импорта не может импортировать,
а шина экспорта не может экспортировать, поэтому ничего не происходит.

## Ввод и вывод через 1 сторону

Предположим, у вас есть устройство, которое может принимать входные данные и выводить результаты через одно отверстие (например, <ItemLink id="charger" />).
Вы можете как вводить ингредиенты, так и извлекать результат, комбинируя два метода подсети кабелей:

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_storage_export_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="4 1 1" max="5 1.3 2">
        (1) Шина импорта: можно отфильтровать
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 1 1" max="3 1.3 2">
        (2) Шина хранения: может быть отфильтрована. Это (и другие шины хранения, которые вы хотите использовать для отправки и получения предметов)
        должно быть единственным хранилищем в сети.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 0 1" max="3 1 2">
        (3) Вещь в которую вы хотите помещать и извлекать: в данном случае — Зарядник.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 1" max="1 1.3 2">
        (4) Шина экспорта: должна быть отфильтрована.
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 1.5" color="#00ff00">
        Источник
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 1.5" color="#00ff00">
        Место назначения
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Интерфейсы

Оказывается, помимо шин импорта и экспорта, существуют [устройства](../ae2-mechanics/devices.md), которые заносят вещи в
[сетевое хранилище](../ae2-mechanics/import-export-storage.md) и извлекают их оттуда!
Здесь актуален <ItemLink id="interface" />. Если вставлен предмет, для которого интерфейс не настроен на хранение, интерфейс
передаст его в сетевое хранилище, которое мы можем использовать аналогично кабелю шина импорта -> шина хранения. Настройка интерфейса на
хранение какого-либо предмета извлечет его из сетевого хранилища, аналогично кабелю шины хранения -> шины экспорта. Интерфейсы могут быть настроены на
хранение одних предметов и не хранение других, что позволяет вам удаленно перемещать предметы через шины хранения, если вы по какой-то причине хотите это сделать.

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/interface_pipes.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        Интерфейс
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        Шина хранения
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3.7 0 2" max="4 1 3">
        Шина хранения
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 2" max="1 1.3 3">
        Шина хранения
  </BoxAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Один-ко-многим и многие-ко-одному (и многие-ко-многим)

Конечно, вам не обязательно использовать только одну <ItemLink id="import_bus" /> или <ItemLink id="export_bus" /> или <ItemLink id="storage_bus" />

<GameScene zoom="3" background="transparent">
<ImportStructure src="../assets/assemblies/many_to_many_pipe.snbt" />

<IsometricCamera yaw="185" pitch="30" />
</GameScene>

## Поставка в несколько мест

Из всего этого мы можем вывести метод отправки ингредиентов с одной стороны <ItemLink id="pattern_provider" /> во многие разные
места, например, в массив машин или на несколько разных сторон одной машины.

Мы не хотим кабель импорт -> хранение или кабель хранение -> экспорт, потому что <ItemLink id="pattern_provider" /> на самом деле никогда 
не содержит ингредиенты. Вместо этого поставщики *передают* ингредиенты в соседние инвентари, поэтому нам нужен какой-то 
соседний инвентарь, который также может импортировать предметы.

Это похоже на... <ItemLink id="interface" />!
Убедитесь, что поставщик находится в режиме направленного или плоского подраздела и/или интерфейс находится в режиме плоского подраздела, чтобы эти два предмета не формировали сетевое
соединение.

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/provider_interface_storage.snbt" />

<BoxAnnotation color="#dddddd" min="2.7 0 1" max="3 1 2">
        Интерфейс (должен быть плоским, не полноблочным)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 4">
        Шины хранения
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0 0" max="1 1 4">
        Места, для которых вы хотите создать шаблон (несколько машин или несколько сторон одной машины)
  </BoxAnnotation>

<IsometricCamera yaw="185" pitch="30" />
</GameScene>