---
navigation:
  parent: example-setups/example-setups-index.md
  title: Автоматизация сброса в воду
  icon: fluix_crystal
---

# Автоматизация рецептов сброса в воду

Обратите внимание, что поскольку здесь используется <ItemLink id="pattern_provider" />, он предназначен для интеграции в вашу установку [автоматического крафта](../ae2-mechanics/autocrafting.md).

В некоторых рецептах требуется бросать предметы в воду (хотя похожая установка может использоваться для бросания предметов в другие места).
Это можно автоматизировать с помощью <ItemLink id="formation_plane" />, <ItemLink id="annihilation_plane" /> и некоторой вспомогательной
инфраструктуры (по сути, это 2 модифицированных [подсети труб](pipe-subnet.md)).

Эта установкаа предназначена для использования в сочетании с [автоматизацией зарядника](charger-automation.md) для предоставления <ItemLink id="charged_certus_quartz_crystal" />.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/throw_in_water.snbt" />

<BoxAnnotation color="#dddddd" min="2 0 1" max="3 1 2">
        (1) Поставщик шаблонов: настройки по умолчанию, с соответствующими шаблонами обработки.

        ![Шаблон флюиса](../assets/diagrams/fluix_pattern_small.png) ![Шаблон дефектного цветущего блока](../assets/diagrams/flawed_budding_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1.7 0 1" max="2 1 2">
        (2) Интерфейс: в настройках по умолчанию.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 .7 1" max="2 1 2">
        (3) Плоскость формирования: настроена на выбрасывание входов в виде предметов.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 2 1" max="2 2.3 2">
        (4) Плоскость уничтожения: не имеет интерфейса настройки.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 1 1" max="3 1.3 2">
        (5) Шина хранения: отфильтрована по выходам шаблонов.
        <Row><ItemImage id="fluix_crystal" scale="2" /><BlockImage id="flawless_budding_quartz" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="3.9 0.5 1.5" color="#00ff00">
        К основной сети и системе авто-зарядки
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/charger_automation.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
    </DiamondAnnotation>

  <IsometricCamera yaw="180" pitch="0" />
</GameScene>

## Настройки и шаблоны

* <ItemLink id="pattern_provider" /> (1) настроен по умолчанию с соответствующими <ItemLink id="processing_pattern" />.
  * Для <ItemLink id="fluix_crystal" /> отлично подходит стандартный рецепт из JEI/REI:

    ![Шаблон флюиса](../assets/diagrams/fluix_pattern.png)

  * Для <ItemLink id="flawed_budding_quartz" />, вероятно, лучше всего создавать его напрямую из <ItemLink id="quartz_block" />,
     что позволяет избежать проблем, когда вход одного рецепта является выходом другого, из-за чего шина хранения не может корректно фильтровать:

    ![Шаблон дефектного цветущего блока](../assets/diagrams/flawed_budding_pattern.png)

* <ItemLink id="interface" /> (2) находится в своей настройке по умолчанию.
* <ItemLink id="formation_plane" /> (3) настроен на выброс входных предметов.
* <ItemLink id="annihilation_plane" /> (4) Не имеет графического интерфейса и не может быть настроен.
* <ItemLink id="storage_bus" /> (5) фильтруется на выходах шаблонов.

## Как это работает

1.  <ItemLink id="pattern_provider" /> подаёт ингредиенты в <ItemLink id="interface" /> на cтороне зелёной подсети.
2.  Интерфейс (так как по умолчанию настроен не хранить что-либо) пытается передать своё содержимое в [сетевое хранилище](../ae2-mechanics/import-export-storage.md)
3.  Единственным хранилищем в зелёной подсети является <ItemLink id="formation_plane" />, который сбрасывает полученные предметы в воду.
4.  <ItemLink id="annihilation_plane" /> в оранжевой подсети пытается подобрать только что сброшенные предметы, но не может, потому что
    <ItemLink id="storage_bus" />, установленный сверху на <ItemLink id="pattern_provider" /> (единственное хранилище в оранжевой подсети), отфильтрован так, чтобы принимать только результаты возможных рецептов.
5.  Предметы проходят свою трансформацию в мире.
6.  Теперь плоскость уничтожения может подобрать предметы перед собой, так как шина хранения разрешает их хранение.
7.  Шина хранения помещает полученные предметы в плоскость формирования, возвращая их в сеть.
