---
navigation:
  parent: example-setups/example-setups-index.md
  title: Автоматизация зарядника
  icon: charger
---

# Автоматизация зарядника

Обратите внимание, что поскольку здесь используется <ItemLink id="pattern_provider" />, он предназначен для интеграции в вашу установку [автоматического крафта](../ae2-mechanics/autocrafting.md).
Если вы просто хотите автоматизировать отдельный <ItemLink id="charger" />, используйте воронки, сундуки и прочее.

Автоматизация <ItemLink id="charger" /> довольно проста. <ItemLink id="pattern_provider" /> помещает ингредиент в зарядник, затем [подсеть кабелей](pipe-subnet.md)
или другой кабель для предметов возвращает результат обратно в поставщик.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/charger_automation.snbt" />

<BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        (1) Поставщик шаблонов: в стандартной настройке с соответствующими шаблонами обработки. Также обеспечивает зарядник питанием.

        ![Шаблон зарядника](../assets/diagrams/charger_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 0" max="1 1.3 1">
        (2) Шина импорта: в настройке по умолчанию.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        (3) Шина хранения: в настройке по умолчанию.
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        В основную сеть
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Настройки

* <ItemLink id="pattern_provider" /> (1) находится в своей настройке по умолчанию с соответствующими <ItemLink id="processing_pattern" />.
  Он также обеспечивает <ItemLink id="charger" /> [энергией](../ae2-mechanics/energy.md), поскольку действует как [кабель](../items-blocks-machines/cables.md).
  
    ![Шаблон зарядника](../assets/diagrams/charger_pattern.png)

* <ItemLink id="import_bus" /> (2) находится в своей настройке по умолчанию.
* <ItemLink id="storage_bus" /> (3) находится в своей настройке по умолчанию.

## Как это работает

1. <ItemLink id="pattern_provider" /> перемещает ингредиенты в <ItemLink id="charger" />.
2. Зарядник выполняет свою работу.
3. <ItemLink id="import_bus" /> в зеленой подсети извлекает результат из зарядника и пытается переместить его для хранения в
   [сетевое хранилище](../ae2-mechanics/import-export-storage.md).
4. Единственным хранилищем в зелёной подсети является <ItemLink id="storage_bus" />, который хранит полученные предметы в поставщике шаблонов, возвращая их в основную сеть.
