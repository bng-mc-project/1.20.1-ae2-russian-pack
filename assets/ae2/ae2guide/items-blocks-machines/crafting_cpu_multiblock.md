---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Мультиблочная структура процессора изготовления
  icon: 1k_crafting_storage
  position: 210
categories:
- devices
item_ids:
- ae2:1k_crafting_storage
- ae2:4k_crafting_storage
- ae2:16k_crafting_storage
- ae2:64k_crafting_storage
- ae2:256k_crafting_storage
- ae2:crafting_accelerator
- ae2:crafting_monitor
- ae2:crafting_unit
---

# Процессор изготовления

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/crafting_cpus.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<Row>
  <BlockImage id="1k_crafting_storage" scale="4" />

  <BlockImage id="crafting_accelerator" scale="4" />

  <BlockImage id="crafting_monitor" scale="4" />

  <BlockImage id="crafting_unit" scale="4" />
</Row>

Процессоры изготовления управляют запросами/задачами изготовления. Они хранят промежуточные ингредиенты во время выполнения многоэтапных задач изготовления
и влияют на размер задач, а также, в некоторой степени, на скорость их выполнения. Подробнее см. [автокрафт](../ae2-mechanics/autocrafting.md). 

Процессоры изготовления управляют запросами или заданиями на изготовление. 

Каждый процессор обрабатывает 1 запрос или задание, поэтому, если вы хотите одновременно запросить вычислительный процессор и 256 гладких камней за раз, вам понадобятся 2 мультиблочных структуры процессора.

Их можно настроить для обработки запросов от игроков, автоматизации (экспорт шин и интерфейсов) или для обоих случаев.

Щелкнув ПКМ, вы откроете интерфейс состояния изготовления, где можно проверить ход выполнения задания, над которым работает процессор.

## Настройки

*   Процессор может быть настроен на принятие запросов только от игроков, только от автоматизации (к примеру <ItemLink id="export_bus" /> с <ItemLink id="crafting_card" />) или от обоих.

## Конструкция

Процессоры изготовления являются мультиблочной структура, она должна состоят из плотных прямоугольных призм без зазоров. Они состоят из нескольких компонентов.

У каждого процессора должен быть хотя бы 1 хранилище для изготовления (и минимальный возможный процессор на самом деле просто единственное хранилище для изготовления на 1К)

# Блок создания

<BlockImage id="crafting_unit" scale="4" />

(Необязательно) Блоки создания просто заполняют пространство в процессоре, это необходимо для того, чтобы сделать его плотной прямоугольной призмой, если у вас не хватает иных компонентов. Также является базовым ингредиентом для других компонентов. 

<RecipeFor id="crafting_unit" />

# Хранилище для изготовления

<Row>
  <BlockImage id="1k_crafting_storage" scale="4" />

  <BlockImage id="4k_crafting_storage" scale="4" />

  <BlockImage id="16k_crafting_storage" scale="4" />

  <BlockImage id="64k_crafting_storage" scale="4" />

  <BlockImage id="256k_crafting_storage" scale="4" />
</Row>

(Обязательно) Хранилища для изготовления доступна во всех стандартных для ячеек размеров (1K, 4K, 16K, 64K, 256K). Они

<Column>
  <Row>
    <RecipeFor id="1k_crafting_storage" />

    <RecipeFor id="4k_crafting_storage" />

    <RecipeFor id="16k_crafting_storage" />
  </Row>

  <Row>
    <RecipeFor id="64k_crafting_storage" />

    <RecipeFor id="256k_crafting_storage" />
  </Row>
</Column>

# Блок совместной обработки изготовления

<BlockImage id="crafting_accelerator" scale="4" />

(Необязательно) Блоки совместной обработки изготовления заставляют систему чаще отправлять партии ингредиентов из <ItemLink id="pattern_provider" />. Это позволяет им не отставать от быстро работающих машин. Примером этого может служить поставщик шаблонов, окруженный несколькими <ItemLink id="molecular_assembler" />, который может поставлять ингредиенты быстрее, чем может обработать один сборщик, и таким образом распределять партии ингредиентов между окружающими сборщиками.

<RecipeFor id="crafting_accelerator" />

# Монитор изготовления

<BlockImage id="crafting_monitor" scale="4" />

(Необязательно) Монитор изготовления показывает задание, которое в данный момент обрабатывает процессор.
Экран может быть покрашен с помощью <ItemLink id="color_applicator" />.

<RecipeFor id="crafting_monitor" />
