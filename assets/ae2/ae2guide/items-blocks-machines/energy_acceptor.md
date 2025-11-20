---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Приёмщик энергии
  icon: energy_acceptor
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:energy_acceptor
---

# Приёмщик энергии

<Row gap="20">
<BlockImage id="energy_acceptor" scale="8" /> 

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/cable_energy_acceptor.snbt" />
</GameScene>
</Row>

Приёмщик энергии конвертирует обычные формы энергии с других технических модов во внутренюю форму [энергии](../ae2-mechanics/energy.md) AE2 - AE. <ItemLink id="controller" /> может также делать это, однако стороны МЭ-регуляторов более востребованы в сети, поэтому всё же лучше использовать приёмщики энергии.

Соотношения конвертации Forge Energy и Techreborn Energy таковы:

*   2 FE = 1 AE (Forge)
*   1 E  = 2 AE (Fabric)

Скорость конвертации полностью зависит от того, сколько AE ваша сеть можеть хранить, это объясняется [здесь](../ae2-mechanics/energy.md)

## Вариации

Приёмщики энергии имеют 2 различных вариации: нормальная и плоская/[подраздел](../ae2-mechanics/cable-subparts.md). Это позволяет делать некоторые установки более компактными.

Приёмщик энергии может быть преобразован с нормальной в плоскую вариацию и наоборот в сетке крафта.

## Рецепт

<RecipeFor id="energy_acceptor" />

<RecipeFor id="cable_energy_acceptor" />