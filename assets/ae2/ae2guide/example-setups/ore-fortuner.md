---
navigation:
  parent: example-setups/example-setups-index.md
  title: Авто-добыча руды с удачей
  icon: minecraft:raw_iron
---

# Авто-добыча руды с удачей

<ItemLink id="annihilation_plane" /> можно зачаровать любым зачарованием кирки, включая удачу, поэтому очевидный вариант использования —
применить удачу к нескольким, а <ItemLink id="formation_plane" /> и <ItemLink id="annihilation_plane" /> будут поочерёдно размещать и
разрушать руду.

Обратите внимание, что поскольку <ItemLink id="import_bus" /> "раскручивается до скорости", установка начнется медленно, а через несколько секунд достигнет полной скорости.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/ore_fortuner.snbt" />

  <BoxAnnotation color="#dddddd" min="2.7 0 2" max="3 1 3">
        (1) Шина импорта: в ней есть несколько карт ускорения.
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 0 2" max="2 1 2.3">
        (2) Плоскости формирования: настройки по умолчанию.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 0 0.7" max="2 1 1">
        (3) Плоскости уничтожения: нет графического интерфейса для настройки, но зачарованы на  удачу.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.7 0 0" max="3 1 1">
        (4) Шина хранения: настройки по умолчанию.
  </BoxAnnotation>

<DiamondAnnotation pos="3.5 0.5 2.5" color="#00ff00">
        Ввод
    </DiamondAnnotation>

<DiamondAnnotation pos="3.5 0.5 0.5" color="#00ff00">
        Ввывод
    </DiamondAnnotation>

<DiamondAnnotation pos="4 0.5 1.5" color="#00ff00">
        В основную сеть
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Настройки

*   <ItemLink id="import_bus" /> (1) содержит несколько <ItemLink id="speed_card" />. Чем больше плоскостей формирования в массиве,
    тем больше нужно таких карт, поскольку они позволяют шине импорта забирать больше предметов одновременно.
*   <ItemLink id="formation_plane" /> (2) находятся в своих настройках по умолчанию.
*   <ItemLink id="annihilation_plane" /> (3) не имеют графического интерфейса и не могут быть настроены, но обладают чарами удачи.
*   <ItemLink id="storage_bus" /> (4) находится в своих настройках по умолчанию.

## Как это работает

1.  <ItemLink id="import_bus" /> в зеленой подсети забирает блоки из первой бочки в [сетевое хранилище](../ae2-mechanics/import-export-storage.md).
2.  Единственным хранилищем в зеленой подсети является <ItemLink id="formation_plane" />, который размещает блоки.
3.  <ItemLink id="annihilation_plane" /> в оранжевой подсети разрушает блоки, применяя к ним удачу.
4.  <ItemLink id="storage_bus" /> в оранжевой подсети сохраняет добытое из руд во второй бочке.
