---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Энергохранилища
  icon: energy_cell
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:energy_cell
- ae2:dense_energy_cell
- ae2:creative_energy_cell
---

# Энергохранилища

<Row gap="20">
  <BlockImage id="energy_cell" scale="8" p:fullness="4" />

  <BlockImage id="dense_energy_cell" scale="8" p:fullness="4" />

  <BlockImage id="creative_energy_cell" scale="8" />
</Row>

Энергохранилища дают сети возможность хранить больший объём [энергии](../ae2-mechanics/energy.md). Некоторое кол-во буффера энергии позволяет смягчить скачки в потреблении энергии, когда к примеру, большой объём предметов перемещается из или в сеть, также больший объём хранимой энергии позволяет сети быть активной, пока энергии не генерируется (к примеру, когда у вас солнечные панели, а на улице ночь) или выдерживать гигантские скачки потребления энергии, к примеру из-за [пространственного хранения](../ae2-mechanics/spatial-io.md).

## Шкала заполнения

<Row>
<BlockImage id="energy_cell" scale="4" p:fullness="0" />
<BlockImage id="energy_cell" scale="4" p:fullness="1" />
<BlockImage id="energy_cell" scale="4" p:fullness="2" />
<BlockImage id="energy_cell" scale="4" p:fullness="3" />
<BlockImage id="energy_cell" scale="4" p:fullness="4" />
</Row>

Шкалы заполнения на сторонах энергохранилищ показывают сколько энергии в нём хранится.

*   0, когда ниже 25% заряда
*   1, когда между 25% и 50% заряда
*   2, когда между 50% и 75% заряда
*   3, когда между 75% и 99% заряда
*   4, когда свыше  99% заряда

## Виды энергохранилищ

*   <ItemLink id="energy_cell" /> могут хранить 200k AE и всего лишь 1 должно хватить для минимизации отключений из-за высокого разового потребления энергии у обычных сетей. 
*   <ItemLink id="dense_energy_cell" /> может хранить 1.6M AE, она может понадобится если вам необходимо запустить сеть с сверхвысоким разовым потребление энергии или ради хранения энергии для массивных установок [пространственного хранения](../ae2-mechanics/spatial-io.md) с астрономическим разовым потреблением энергии.
*   <ItemLink id="creative_energy_cell" /> это творческий предмет для тестирования, хранящий ***ВСЮ МОЩЬ ВСЕЛЕННОЙ!*** Ну... или нескончаемую энергию, какая разница. 

## Рецепты

<Row>
  <RecipeFor id="energy_cell" />

  <RecipeFor id="dense_energy_cell" />
</Row>
