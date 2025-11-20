---
navigation:
  parent: example-setups/example-setups-index.md
  title: Продвинутая ферма истинного кварца
  icon: certus_quartz_crystal
  position: 120
---

# Продвинутая ферма истинного кварца

По сути, это просто [Полуавтоматическая ферма истинного кварца](semiauto-certus-farm.md), только полностью интегрированная в вашу МЭ систему.

Вместо того, чтобы иметь большой запас цветущих блоков и время от времени обновлять их вручную,
в этой установке используются [Авто-зарядник](charger-automation.md) и [Автоматизация сброса в воду](throw-in-water-automation.md)
для автоматического выполнения этой задачи.

**ЭТО СЛОЖНАЯ КОНСТРУКЦИЯ, В КОТОРОЙ ОДНИ ЭЛЕМЕНТЫ СКРЫТЫ ЗА ДРУГИМИ, ПОВОРАЧИВАЙТЕ КАМЕРУ, ЧТОБЫ РАССМОТРЕТЬ ЕЕ СО ВСЕХ СТОРОН**

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/advanced_certus_farm.snbt" />

  <BoxAnnotation color="#ddaaaa" min="3.7 2 1" max="4 3 2">
        (1) Плоскость уничтожения №1: нет графического интерфейса для настройки, но может быть зачарована на "Удачу".
  </BoxAnnotation>

  <BoxAnnotation color="#ddaaaa" min="2 2 1.7" max="3 3 2">
        (2) Шина хранения №1: отфильтровано на кристалл истинного кварца.
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 2.5 1.5" color="#ff0000">
    Подсеть разрушения друз
  </DiamondAnnotation>

  <BoxAnnotation color="#aaddaa" min="3.7 1 1" max="4 2 2">
        (3) Плоскость уничтожения № 2: нет графического интерфейса для настройки, но зачарован на "Шелковое касание".
  </BoxAnnotation>

  <BoxAnnotation color="#aaddaa" min="2 1 1.7" max="3 2 2">
        (4) Шина хранения №2: отфильтровано на кристалл истинного кварца.
        <BlockImage id="quartz_block" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 1.5 1.5" color="#00ff00">
    Подсеть разрушения блоков истинного кварца
  </DiamondAnnotation>

  <BoxAnnotation color="#ffddaa" min="4 0.7 1" max="5 1 2">
        (5) Плоскость формирования: имеет настройки по умолчанию.
  </BoxAnnotation>

  <BoxAnnotation color="#ffddaa" min="2 0.7 2" max="3 1 3">
        (6) Шина импорта: отфильтровано на Потресканный/Несовершенный цветущий блок истинного кварца.
        <BlockImage id="flawed_budding_quartz" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 0.5 1.5" color="#ddcc00">
    Подсеть размещения цветущих блоков истинного кварца
  </DiamondAnnotation>

  <BoxAnnotation color="#aaaadd" min="1.7 2 2" max="2 3 3">
        (7) Шина хранения № 3: фильтруется на кристаллы истинного кварца. Имеет приоритет выше, чем ваше основное хранилище.
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#aaaadd" min="2 1 2" max="3 2 3">
        (8) Интерфейс: установлен для хранения 1 Потресканного/Несовершенного цветущего блока истинного кварца, имеет карту изготовления.
        <Row><BlockImage id="flawed_budding_quartz" scale="2" /> <ItemImage id="crafting_card" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="1.5 0.5 0" color="#00ff00">
        К основной сети, автоматизации зарядки и автоматизации бросания в воду.
        <Row>
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/charger_automation.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/throw_in_water.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
        </Row>
    </DiamondAnnotation>

  <IsometricCamera yaw="165" pitch="5" />
</GameScene>

## Настройки

### Разрушение друз:

* Первая <ItemLink id="annihilation_plane" /> (1) не имеет графического интерфейса и не может быть настроена, но может быть зачарован на "Удачу".
* Первая <ItemLink id="storage_bus" /> (2) фильтруется на <ItemLink id="certus_quartz_crystal" />.

### Разрушение блоков истинного кварца:

* Вторая <ItemLink id="annihilation_plane" /> (3) не имеет графического интерфейса и не может быть настроена, но должна быть зачарована на "Шелковое касание".
* Вторая <ItemLink id="storage_bus" /> (4) фильтруется на <ItemLink id="quartz_block" />.

### Размещение цветущих блоков истинного кварца:

* <ItemLink id="formation_plane" /> (5) имеет настройки по умолчанию.
* <ItemLink id="import_bus" /> (6) отфильтрована на <ItemLink id="flawed_budding_quartz" />.

### В основную сеть:

* Третья <ItemLink id="storage_bus" /> (7) фильтруется на <ItemLink id="certus_quartz_crystal" />, и его
  [приоритет](../ae2-mechanics/import-export-storage.md#приоритет-хранения) устанавливается выше, чем у вашего основного хранилища.
* <ItemLink id="interface" /> (8) настроен на хранение 1 Потресканного/Несовершенного цветущего блока истинного кварца и имеет <ItemLink id="crafting_card" />.

## Как это работает

### Разрушение друз:

Подсеть разрушения друз работает очень похожа на подсеть в [Простой ферме истинного кварца](simple-certus-farm.md).

1. <ItemLink id="annihilation_plane" /> пытается разрушить то, что находится перед ним, но может разрушить только <ItemLink id="quartz_cluster" />,
   поскольку единственным хранилищем в подсети является <ItemLink id="storage_bus" />, отфильтрованный на <ItemLink id="certus_quartz_crystal" />.
2. <ItemLink id="storage_bus" /> хранит кристаллы истинного кварца в бочке.

### Разрушение блоков истинного кварца:

Подсеть разрушения блоков истинного кварца служит для разрушения истощенного цветущего блока, как только он превращается в обычный <ItemLink id="quartz_block" />.
Она работает аналогично разрушителю друз.

1. <ItemLink id="annihilation_plane" /> пытается разрушить то, что находится перед ним, но может разрушить только <ItemLink id="quartz_block" />,
 поскольку единственным хранилищем в подсети является <ItemLink id="storage_bus" />, отфильтрованный на <ItemLink id="quartz_block" />. 
Плоскость уничтожения должна иметь зачарование "Шелковое касание", чтобы блок не деградировал при разрушении, и таким образом плоскость уничтожения не разрушила его преждевременно.
2. <ItemLink id="storage_bus" /> хранит блок истинного кварца в <ItemLink id="interface" />, позволяя
   [Автоматизации сброса в воду](throw-in-water-automation.md) использовать его для создания нового <ItemLink id="flawed_budding_quartz" />.

### Размещение цветущих блоков истинного кварца:

Подсеть размещения цветущих блоков истинного кварца служит для размещения нового <ItemLink id="flawed_budding_quartz" />, когда подсеть разрушения  разбивает старый истощенный блок.

1. <ItemLink id="import_bus" /> импортирует цветущий блок из <ItemLink id="interface" /> в [сетевое хранилище](../ae2-mechanics/import-export-storage.md).
2. Единственным хранилищем в подсети является <ItemLink id="formation_plane" />, который размещает цветущий блок.

### В основную сеть

* <ItemLink id="storage_bus" /> предоставляет основной сети (а также [Авто-заряднику](charger-automation.md)) доступ ко всем кристаллам истинного кварца в бочке. Он установлен на
  высокий [приоритет](../ae2-mechanics/import-export-storage.md#приоритет-хранения), чтобы кристаллы истинного кварца предпочтительно
  возвращались в бочку, а не в ваше основное хранилище.
* <ItemLink id="interface" /> предоставляет подсети, размещающей цветущие блоки истинного кварца, доступ к <ItemLink id="flawed_budding_quartz" />, а
    подсети, разрушающей блоки истинного кварца, — способ вернуть истощенные блоки в основную сеть. 
    <ItemLink id="crafting_card" /> позволяет интерфейсу запрашивать новые цветущие блоки из установки [автоматического крафта](../ae2-mechanics/autocrafting.md) основной сети.