---
navigation:
  parent: example-setups/example-setups-index.md
  title: Полуавтоматическая ферма истинного кварца
  icon: certus_quartz_crystal
  position: 115
---

# Полуавтоматическая ферма истинного кварца

К сожалению, для полной автоматизации работы [простой фермы истинного кварца](simple-certus-farm.md) требуется <ItemLink id="flawless_budding_quartz" />.
Для этого требуется либо [пространственный ввод/вывод](../ae2-mechanics/spatial-io.md), либо постройка фермы на [метеорите](../ae2-mechanics/meteorites.md).

Однако AE2 может размещать и разрушать блоки, поэтому, возможно,
ваша ферма сможет *заменить цветущие блоки за вас*. (Вам придется периодически вставлять некоторые
<ItemLink id="flawed_budding_quartz" /> в входную бочку и извлекать <ItemLink id="quartz_block" /> из 
бочки с исчерпанными цветущими блоками истинным кварцем)

Чтобы сделать это полностью автоматически, см. [Продвинутая ферма истинного кварца](advanced-certus-farm.md).

Эта ферма немного сложнее, чем [простая ферма истинного кварца](simple-certus-farm.md), потому что на самом деле она представляет собой
3 отдельных установки, объединенные воедино.

**ЭТО СЛОЖНАЯ КОНСТРУКЦИЯ, В КОТОРОЙ ОДНИ ПРЕДМЕТЫ СКРЫТЫ ЗА ДРУГИМИ, ПОВОРАЧИВАЙТЕ КАМЕРУ, ЧТОБЫ РАССМОТРЕТЬ ЕЕ СО ВСЕХ СТОРОН**

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/semiauto_certus_farm.snbt" />

  <BoxAnnotation color="#ddaaaa" min="3.7 2 1" max="4 3 2">
        (1) Плоскость уничтожения №1: нет графического интерфейса для настройки, но может быть зачарована на "Удачу".
  </BoxAnnotation>

  <BoxAnnotation color="#ddaaaa" min="2 2 1" max="2.3 3 2">
        (2) Шина хранения №1: отфильтрована на кристалл истинного кварца.
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 2.5 1.5" color="#ff0000">
    Подсеть разрушения друз
  </DiamondAnnotation>

  <BoxAnnotation color="#aaddaa" min="3.7 1 1" max="4 2 2">
        (3) Плоскость уничтожения №2: нет графического интерфейса для настройки, но зачарован на "Шелковое касание".
  </BoxAnnotation>

  <BoxAnnotation color="#aaddaa" min="2 1 1" max="2.3 2 2">
        (4) Шина хранения №2: отфильтрована на блок истинного кварца.
        <BlockImage id="quartz_block" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 1.5 1.5" color="#00ff00">
    Подсеть разрушения блоков истинного кварца
  </DiamondAnnotation>

  <BoxAnnotation color="#ffddaa" min="4 0.7 1" max="5 1 2">
        (5) Плоскость формирования: имеет настройки по умолчанию.
  </BoxAnnotation>

  <BoxAnnotation color="#ffddaa" min="2 0 1" max="2.3 1 2">
        (6) Шина импорта:  имеет настройки по умолчанию.
  </BoxAnnotation>

  <DiamondAnnotation pos="3 0.5 1.5" color="#ddcc00">
    Подсеть для размещения цветущих блоков истинного кварца.
  </DiamondAnnotation>

  <BoxAnnotation color="#aaaadd" min="0.7 2 1" max="1 3 2">
        (7) Шина хранения №3: фильтруется на кристалл истинного кварца. Имеет приоритет выше, чем ваше основное хранилище.
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

    <DiamondAnnotation pos="1.5 0.5 1.5" color="#00ff00">
        Вставьте вручную Потресканных/Несовершенный цветущий блок истинного кварца.
        <BlockImage id="flawed_budding_quartz" scale="2" />
    </DiamondAnnotation>

    <DiamondAnnotation pos="1.5 1.5 1.5" color="#00ff00">
        Вручную извлеките блок истинного кварца.
        <BlockImage id="quartz_block" scale="2" />
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0" color="#00ff00">
        В основную сеть
    </DiamondAnnotation>

  <IsometricCamera yaw="165" pitch="5" />
</GameScene>

## Настройки

### Разрушение друз:

* Первая <ItemLink id="annihilation_plane" /> (1) не имеет графического интерфейса и не может быть настроена, но может быть зачарован на "Удачу".
* Первая <ItemLink id="storage_bus" /> (2) фильтруется на <ItemLink id="certus_quartz_crystal" />.

### Разрушение блоков истинного кварца:

* Вторая <ItemLink id="annihilation_plane" /> (3) не имеет графического интерфейса и не может быть настроена, но должен быть зачарован на "Шелковое касание".
* Вторая <ItemLink id="storage_bus" /> (4) фильтруется на <ItemLink id="quartz_block" />.

### Размещение цветущих блоков истинного кварца:

* <ItemLink id="formation_plane" /> (5) имеет настройки по умолчанию.
* <ItemLink id="import_bus" /> (6) имеет настройки по умолчанию.

### В основную сеть:

* Третий <ItemLink id="storage_bus" /> (7) фильтруется на <ItemLink id="certus_quartz_crystal" />, и его
  [приоритет](../ae2-mechanics/import-export-storage.md#приоритет-хранения) устанавливается выше, чем у вашего основного хранилища.

## Как это работает

### Разрушение друз:

Подсеть разрушения друз работает очень похоже на подсеть в [простой ферме истинного кварца](simple-certus-farm.md).

1. <ItemLink id="annihilation_plane" /> пытается разрушить то, что находится перед ним, но может разрушить только <ItemLink id="quartz_cluster" />,
   поскольку единственным хранилищем в подсети является <ItemLink id="storage_bus" />, отфильтрованный на <ItemLink id="certus_quartz_crystal" />.
2. <ItemLink id="storage_bus" /> хранит кристаллы истинного кварца в бочке.

### Разрушение блоков истинного кварца:

Подсеть разрушения блоков истинного кварца служит для разрушения истощенного цветущего блока, как только он превращается в обычный <ItemLink id="quartz_block" />.
Она работает аналогично разрушению друз.

1. <ItemLink id="annihilation_plane" /> пытается разрушить то, что находится перед ним, но может разрушить только <ItemLink id="quartz_block" />,
   поскольку единственным хранилищем в подсети является <ItemLink id="storage_bus" />, отфильтрованный на <ItemLink id="quartz_block" />.
  Плоскость уничтожения должна иметь "Шелковое касание", чтобы блок не разрушился при разрушении, и, таким образом, плоскость уничтожения не разрушила его преждевременно.
2. <ItemLink id="storage_bus" /> помещает блок истинного кварца в бочку с исчерпанными цветущими блоками истинного кварца; вам придётся вручную сбрасывать его в воду вместе с <ItemLink id="charged_certus_quartz_crystal" />, чтобы восстановить.

### Размещение цветущих блоков истинного кварца

Подсеть размещения цветущих блоков истинного кварца служит для размещения нового <ItemLink id="flawed_budding_quartz" />, когда подсеть разрушения разбивает старый истощенный блок.

1. <ItemLink id="import_bus" /> Импортирует цветущий блок истинного кварца из входной бочки.
2. Единственным хранилищем в подсети является <ItemLink id="formation_plane" />, который размещает цветущий блок.

### В Основную сеть

* <ItemLink id="storage_bus" /> предоставляет основной сети (а также [Авто-зарядник](charger-automation.md)) доступ ко всем кристаллам истинного кварца в бочке. Он установлен на
  высокий [приоритет](../ae2-mechanics/import-export-storage.md#приоритет-хранения), чтобы кристаллы истинного кварца предпочтительно
  возвращались в бочку, а не в ваше основное хранилище.