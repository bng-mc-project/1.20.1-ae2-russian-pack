---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Фасады
  icon: facade
  icon_nbt: '{item: "minecraft:stone"}'
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:facade
---

# Фасады

Фасады могут быть использованы для создания более "чистого" окружения твоей базы. Они могут покрывать кабель обоих размеров и могут быть сделаны из множества блоков

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/facades_1.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Они могут покрывать все стороны кабеля, но будут пропускать [подразделы](../ae2-mechanics/cable-subparts.md) и соединения кабелей сквозь себя.

<GameScene zoom="6"  interactive={true}>
  <ImportStructure src="../assets/assemblies/facades_2.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Фасады могут быть использованы для создания более аутентичного окружения базы или создания блоков с различными текстурами на каждой стороне.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/facades_3.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Прятание фасадов

Фасады будут спрятаны, пока вы держите <a href="network_tool.md">сетевой инструмент</a> в любой из ваших рук

Вы можете взаимодействовать с блоками за спрятаными фасадами без необходимости заранее убирать их.

## Рецепт

Поместите блок, чью текстуру вы хотите видеть в центр, а по бокам 4 <ItemLink id="cable_anchor" />.

![Facade Recipe](../assets/diagrams/facade_recipe.png)
