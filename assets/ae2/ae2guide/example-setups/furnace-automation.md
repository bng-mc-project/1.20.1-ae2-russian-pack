---
navigation:
  parent: example-setups/example-setups-index.md
  title: Автоматизация печки
  icon: minecraft:furnace
---

# Автоматизация печки

Обратите внимание, что поскольку здесь используется <ItemLink id="pattern_provider" />, он предназначен для интеграции в вашу установку [автоматического крафта](../ae2-mechanics/autocrafting.md).
Если вы просто хотите автоматизировать работу печи, используйте воронки, сундуки и прочее.

Автоматизация <ItemLink id="minecraft:furnace" /> немного сложнее, чем автоматизация более простых машин, таких как [зарядник](../example-setups/charger-automation.md).
Печь требует ввода с двух разных сторон и извлечения с третьей. Предмет, который нужно расплавить, необходимо переместить через верхнюю часть,
топливо — через боковую часть, а переплавленный предмет — извлечь из нижней части. 

Это можно сделать с помощью <ItemLink id="pattern_provider" />
сверху, <ItemLink id="export_bus" /> сбоку для постоянной подачи топлива и <ItemLink id="import_bus" />
внизу, чтобы переместить готовый продукт в сеть. Однако для этого используются 3 [канала](../ae2-mechanics/channels.md).

Вот как это можно сделать с помощью всего одного канала:

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/furnace_automation.snbt" />

<BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        
(1) Поставщик шаблонов: направленный вариант, с использованием кварцевого ключа, с соответствующими шаблонами обработки.

        ![Шаблон железа](../assets/diagrams/furnace_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        (2) Интерфейс: в настройке по умолчанию.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="1.3 2 1">
        (3) Шина хранения № 1: отфильтрованный на уголь.
        <ItemImage id="minecraft:coal" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 2 0" max="1 2.3 1">
        (4) Шина хранения № 2: отфильтрован для внесения угля в черный список с помощью карты-инвертера
        <Row><ItemImage id="minecraft:coal" scale="2" /><ItemImage id="inverter_card" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        В основную сеть
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Настройки

* <ItemLink id="pattern_provider" /> (1) находится в своей настройке по умолчанию с соответствующим <ItemLink id="processing_pattern" />.
    Он становится направленным благодаря использованию на нём <ItemLink id="certus_quartz_wrench" />.

  ![Шаблон железа](../assets/diagrams/furnace_pattern.png)

* <ItemLink id="interface" /> (2) имеет настройку по умолчанию.
* Первая <ItemLink id="storage_bus" /> (3) отфильтровывается на угль или любого другого топлива, которое вы хотите использовать.
* Вторая <ItemLink id="storage_bus" /> (4) фильтруется, чтобы занести в черный список используемое вами топливо, с помощью <ItemLink id="inverter_card" />.

## Как это работает

1. <ItemLink id="pattern_provider" /> переносит ингредиенты в <ItemLink id="interface" />.
   (Фактически, в целях оптимизации данные проходят непосредственно через шины хранения, как если бы они были продолжением граней поставщика. Предметы никогда не попадают в интерфейс.)
2. Интерфейс настроен так, что ничего не сохраняет, поэтому он пытается переместить ингредиенты в [сетевое хранилище](../ae2-mechanics/import-export-storage.md).
3. Единственным хранилищем в зеленой подсети является <ItemLink id="storage_bus" />. Отфильтрованная шина на угль, помещает уголь в топливный слот печи через боковую поверхность.
   Шина, отфильтрованная на НЕ угль, помещает предметы, подлежащие плавке, в верхний слот через верхнюю поверхность.
4. Печь делает свою работу
5. Воронка извлекает готовый предмет из нижней части печи и помещает их в слоты возврата поставщика, возвращая их в основную сеть.
