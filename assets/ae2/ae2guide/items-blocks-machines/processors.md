---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Процессоры
  icon: logic_processor
  position: 010
categories:
- misc ingredients blocks
item_ids:
- ae2:logic_processor
- ae2:calculation_processor
- ae2:engineering_processor
- ae2:printed_silicon
- ae2:printed_logic_processor
- ae2:printed_calculation_processor
- ae2:printed_engineering_processor
- ae2:silicon
---

# Процессоры

<Row>
  <ItemImage id="logic_processor" scale="4" />

  <ItemImage id="calculation_processor" scale="4" />

  <ItemImage id="engineering_processor" scale="4" />
</Row>

Процессоры являются одними из основных компонентов AE2 [устройств](../ae2-mechanics/devices.md) и машин. Они также являются одним из ваших первых трудных для автоматизации предметов. Всего существует 3 вида процессоров, сделанные из золота, <ItemLink id="certus_quartz_crystal" /> и алмазов. Они создаются при помощи [печатей](presses.md) в <ItemLink id="inscriber" />, с многоступенчатым процессом (обычно достигается через создание серии вырезателей и отфильтрованных линий передачи предметов)

## Шаги изготовления

<Column gap="5">
  1.  Создайте/добудьте следующие ингредиенты: кремний, редстоуновая пыль, золото, <ItemLink id="certus_quartz_crystal" />, алмаз.

  <RecipeFor id="silicon" />

  <br />

  2.  Спрессуйте необходимые компоненты печатной платы

  <Row>
    <RecipeFor id="printed_silicon" />

    <RecipeFor id="printed_logic_processor" />
  </Row>

  <Row>
    <RecipeFor id="printed_calculation_processor" />

    <RecipeFor id="printed_engineering_processor" />
  </Row>

  <br />

  3.  Финальная сборка

  <Row>
    <RecipeFor id="logic_processor" />

    <RecipeFor id="calculation_processor" />
  </Row>

  <RecipeFor id="engineering_processor" />
</Column>
