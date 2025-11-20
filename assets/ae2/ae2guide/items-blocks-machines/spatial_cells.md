---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Пространственные ячейки
  icon: spatial_storage_cell_128
  position: 410
categories:
- tools
item_ids:
- ae2:spatial_storage_cell_2
- ae2:spatial_storage_cell_16
- ae2:spatial_storage_cell_128
- ae2:spatial_cell_component_2
- ae2:spatial_cell_component_16
- ae2:spatial_cell_component_128
---

# Пространственные ячейки хранения

  <Row>
    <ItemImage id="spatial_storage_cell_2" scale="4" />

    <ItemImage id="spatial_storage_cell_16" scale="4" />

    <ItemImage id="spatial_storage_cell_128" scale="4" />
  </Row>

Пространственные ячейки хранения используются для [хранения физическим объёмов пространства](../ae2-mechanics/spatial-io.md). Используются в <ItemLink id="spatial_io_port" />. 

В отличие от [ячеек хранения](../items-blocks-machines/storage_cells.md), пространственные ячейки не могут быть форматированы.

Опять же, **ВЫ НЕ МОЖЕТЕ СБРОСИТЬ, ПЕРЕФОРМАТИРОВАТЬ ИЛИ ИЗМЕНИТЬ РАЗМЕР ПРОСТРАНСТВЕННОЙ ЯЧЕЙКИ ПОСЛЕ
ЕЕ ИСПОЛЬЗОВАНИЯ.** Создайте новую ячейку, если хотите использовать другие размеры. 


## Рецепты

  <Row>
    <Recipe id="network/cells/spatial_storage_cell_2_cubed_storage" />

    <Recipe id="network/cells/spatial_storage_cell_16_cubed_storage" />

    <Recipe id="network/cells/spatial_storage_cell_128_cubed_storage" />
  </Row>

# Корпусы

Ячейки создаются из пространственного компонента и корпуса или рецептом корпуса вокруг пространственного компонента:

<Row>
  <Recipe id="network/cells/spatial_storage_cell_2_cubed" />

  <Recipe id="network/cells/spatial_storage_cell_2_cubed_storage" />
</Row>

Корпуса сами по себе создаются так:

  <RecipeFor id="item_cell_housing" />

# Пространственные компоненты

Пространственные компоненты являются ядром пространственных ячеек хранения. Каждый уровень увеличевает размер объёма, который может храниться в 8 раз.

  <Row>
    <RecipeFor id="spatial_cell_component_2" />

    <RecipeFor id="spatial_cell_component_16" />

    <RecipeFor id="spatial_cell_component_128" />
  </Row>