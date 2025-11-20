---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Молекулярный сборщик
  icon: molecular_assembler
  position: 310
categories:
- machines
item_ids:
- ae2:molecular_assembler
---

# Молекулярный сборщик

<BlockImage id="molecular_assembler" scale="8" />

Молекулярный сборщик принимает введенные в него предметы и выполняет операцию, определенную соседним <ItemLink id="pattern_provider" />,
или вставленным <ItemLink id="crafting_pattern" />, <ItemLink id="smithing_table_pattern" /> или <ItemLink id="stonecutting_pattern" />,
а затем отправляет результат в соседние инвентари.

Этот сборщик имеет схему изготовления, которая определяет рецепт 1 дубовое бревно = 4 дубовые доски. Когда дубовые бревна подаются в верхнюю воронку,
сборщик изготавливает и выбрасывает дубовые доски в нижнюю воронку.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/standalone_assembler.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Основное назначение молекулярного сборщика

Однако их основное использование — рядом с <ItemLink id="pattern_provider" />. Поставщики шаблонов в этом случае ведут себя особым образом
и отправляют информацию о соответствующем шаблоне вместе с ингредиентами соседним сборщикам. Поскольку сборщики автоматически выбрасывают готовые предметы в соседние инвентари (и, таким образом, в слоты возврата поставщика шаблонов), сборщик на поставщике шаблонов
— это все, что нужно для автоматизации шаблонов изготовления.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/assembler_tower.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Улучшения

Молекулярный сборщик поддерживает следующие [улучшения](upgrade_cards.md):

*   <ItemLink id="speed_card" />

## Рецепт

<RecipeFor id="molecular_assembler" />

## Примечание

Optifine отключает функции “передачи в соседние инвентари”, поэтому большинство схем автоматичесого крафта с использованием сборщиков не будут работать.