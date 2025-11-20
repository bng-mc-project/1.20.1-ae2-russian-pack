---
navigation:
  parent: example-setups/example-setups-index.md
  title: Простая ферма истинного кварца
  icon: certus_quartz_crystal
  position: 110
---

# Простая ферма истинного кварца

Как упоминалось в [Выращивании истинного кварца](../ae2-mechanics/certus-growth.md), автоматизация сбора <ItemLink id="certus_quartz_crystal" />
осуществляется с помощью <ItemLink id="annihilation_plane" /> и <ItemLink id="storage_bus" />. 
<ItemLink id="growth_accelerator" /> используются для значительного ускорения роста цветущих блоков истинного кварца, а затем плоскости уничтожения
разрушают полностью выросшие <ItemLink id="quartz_cluster" />. Они фильтруются с помощью подозрительно удачной особенности, благодаря которой незрелые
бутоны истинного кварца выпадают <ItemLink id="certus_quartz_dust" /> вместо того, чтобы не выпадать вообще.

Эта ферма работает полностью автоматически с <ItemLink id="flawless_budding_quartz" />, но в случае с потресканным/несовершенным, потресканным/сколотым и поврежденным
цветущим блоком истинного кварца вам придется заменить цветущий блок вручную. Или, как описано в [Полуавтоматической ферме истинного кварца](semiauto-certus-farm.md)
и [Продвинутой ферме истинного кварца](advanced-certus-farm.md), автоматически. 

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/simple_certus_farm.snbt" />

  <BoxAnnotation color="#dddddd" min="3.7 1 1" max="4 2 2">
        (1) Плоскость уничтожения: нет графического интерфейса для настройки, но может быть зачарована на "Удачу".
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 1" max="3.3 2 2">
        (2) Шина хранения № 1: отфильтрована на кристалл истинного кварца. 
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 .7" max="2 2 1">
        (3) Шина хранения № 2: отфильтрована на кристалл истинного кварца. Имеет приоритет выше, чем основное хранилище.
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

<DiamondAnnotation pos="1 0.5 0.5" color="#00ff00">
        В основную сеть
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Настройки

* Первый <ItemLink id="annihilation_plane" /> (1) не имеет графического интерфейса и не может быть настроен, но может быть зачарован на "Удачу".
* Первый <ItemLink id="storage_bus" /> (2) фильтруется на <ItemLink id="certus_quartz_crystal" />.
* Второй <ItemLink id="storage_bus" /> (3) фильтруется на <ItemLink id="certus_quartz_crystal" />, и его
  [приоритет](../ae2-mechanics/import-export-storage.md#приоритет-хранения) устанавливается выше, чем у основного хранилища.

## Как это работает

1. <ItemLink id="annihilation_plane" /> пытается разрушить то, что находится перед ним, но может разрушить только <ItemLink id="quartz_cluster" />,
   поскольку единственным хранилищем в подсети является <ItemLink id="storage_bus" />, отфильтрованный на <ItemLink id="certus_quartz_crystal" />.
2. Первый <ItemLink id="storage_bus" /> хранит кристаллы истинного кварца в бочке.
3. Второй <ItemLink id="storage_bus" /> предоставляет основной сети доступ ко всем кристаллам истинного кварца в бочке. Он установлен на
   высокий [приоритет](../ae2-mechanics/import-export-storage.md#приоритет-хранения), чтобы кристаллы истинного кварца предпочтительно
   возвращались в бочку, а не в ваше основное хранилище.
