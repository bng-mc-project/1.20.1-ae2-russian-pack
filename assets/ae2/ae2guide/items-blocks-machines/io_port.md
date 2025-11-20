---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: МЭ порт ввода/вывода
  icon: io_port
  position: 210
categories:
- devices
item_ids:
- ae2:io_port
---

# МЭ порт ввода/вывода

<BlockImage id="io_port" p:powered="true" scale="8" />

МЭ порт ввода/вывода позволяет быстро заполнять и опустошать [ячейки хранения](../items-blocks-machines/storage_cells.md) в и из
[сетевого хранилища](../ae2-mechanics/import-export-storage.md).

Может быть повёрнут с помощью <ItemLink id="certus_quartz_wrench" />.

## Настройки

*   МЭ порт ввода/вывода может быть настроен, чтобы перемещать ячейка в слот вывода, когда она пуста, полна или когда задача сделана.
*   Если <ItemLink id="redstone_card" /> вставлена, то с помощью редстоуна можно будет управлять устройством.
*   В центре графического интерфейса находится стрелка для установления направления для передачи предметов, из ячейки в [сетевое хранилище](../ae2-mechanics/import-export-storage.md),
    либо из хранилище в ячейку.

## Улучшения

МЭ порт ввода/вывода поддерживает следующие [улучшения](upgrade_cards.md):

*   <ItemLink id="speed_card" /> увеличивает объём предметов, которые порт может переместить за операцию
*   <ItemLink id="redstone_card" /> добавляет управление устройством с помощью редстоуна. 

## Рецепт

<RecipeFor id="io_port" />
