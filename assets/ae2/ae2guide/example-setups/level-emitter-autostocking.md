---
navigation:
  parent: example-setups/example-setups-index.md
  title: Автозаполнение излучателя уровня
  icon: level_emitter
---

# Автозаполнение излучателя уровня

Можно задаться вопросом: "Как поддерживать определённое количество предмета на складе, автоматически создавая больше по мере необходимости?"

Одним из решений является использование <ItemLink id="export_bus" />, <ItemLink id="level_emitter" /> и <ItemLink id="crafting_card" /> для автоматического запроса новых предметов
из установки [автоматического крафта](../ae2-mechanics/autocrafting.md) вашей сети. Эта установка предназначена для поддержания большого количества одного предмета.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/level_emitter_autostocking.snbt" />

  <BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        (1) Шина экспорта: отфильтрована на нужный предмет. Имеет редстоуновую карту и карту изготовления. Режим редстоуна установлен на
        "Активна при сигнале", Поведение крафта установлено на "Не использовать запасённые предметы".
        <Row><ItemImage id="redstone_card" scale="2" /> <ItemImage id="crafting_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0.7 1 0" max="1 2 1">
        (2) Излучатель уровня: настроен на нужный предмет и количество, установлен режим "Излучать при уровне ниже лимита".
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        (3) Интерфейс: в настройке по умолчанию.
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        В основной сети
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Настройки

* <ItemLink id="export_bus" /> (1) отфильтрован на нужный предмет. В него вставлены <ItemLink id="redstone_card" /> и <ItemLink id="crafting_card" />.
  Режим редстоуна установлен на "Активна при сигнале", поведение крафта установлено на "Не использовать запасённые предметы".
* <ItemLink id="level_emitter" /> (2) настроен на нужный предмет и количество, установлен режим "Излучать при уровне ниже лимита".
* <ItemLink id="interface" /> (3) находится в настройке по умолчанию.

## Как это работает

1. Если количество нужного предмета в [сетевом хранилище](../ae2-mechanics/import-export-storage.md) ниже значения, указанного в 
   <ItemLink id="level_emitter" />, излучатель уровня выдаст сигнал редстоуна.
2. При получении сигнала редстоуна (и благодаря <ItemLink id="crafting_card" /> и настройке "Не использовать запасённые предметы")
   <ItemLink id="export_bus" /> запросит, чтобы установка [автоматического крафта](../ae2-mechanics/autocrafting.md) сети создала
   большее количество нужного предмета, а затем экспортировала его.
3. При поступлении предмета (и если внутренний инвентарь не настроен на хранение), <ItemLink id="interface" /> отправит этот предмет в сетевое хранилище.