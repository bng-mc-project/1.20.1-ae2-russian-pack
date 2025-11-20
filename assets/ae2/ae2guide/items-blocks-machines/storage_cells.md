---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Ячейки хранения
  icon: item_storage_cell_1k
  position: 410
categories:
- tools
item_ids:
- ae2:item_cell_housing
- ae2:fluid_cell_housing
- ae2:cell_component_1k
- ae2:cell_component_4k
- ae2:cell_component_16k
- ae2:cell_component_64k
- ae2:cell_component_256k
- ae2:item_storage_cell_1k
- ae2:item_storage_cell_4k
- ae2:item_storage_cell_16k
- ae2:item_storage_cell_64k
- ae2:item_storage_cell_256k
- ae2:fluid_storage_cell_1k
- ae2:fluid_storage_cell_4k
- ae2:fluid_storage_cell_16k
- ae2:fluid_storage_cell_64k
- ae2:fluid_storage_cell_256k
---

# Ячейки хранения
<Column>
  <Row>
    <ItemImage id="item_storage_cell_1k" scale="4" />

    <ItemImage id="item_storage_cell_4k" scale="4" />

    <ItemImage id="item_storage_cell_16k" scale="4" />

    <ItemImage id="item_storage_cell_64k" scale="4" />

    <ItemImage id="item_storage_cell_256k" scale="4" />
  </Row>

  <Row>
    <ItemImage id="fluid_storage_cell_1k" scale="4" />

    <ItemImage id="fluid_storage_cell_4k" scale="4" />

    <ItemImage id="fluid_storage_cell_16k" scale="4" />

    <ItemImage id="fluid_storage_cell_64k" scale="4" />

    <ItemImage id="fluid_storage_cell_256k" scale="4" />
  </Row>
</Column>

Ячейки хранения являются одними из основных методов хранения чего-либо в Applied Energistics. Они вставляются в <ItemLink id="drive" /> или <ItemLink id="chest" />.
или <ItemLink id="chest" />.

См. раздел [Байты и типы](../ae2-mechanics/bytes-and-types.md) для объяснения их емкости в байтах и типах.

Компоненты хранения можно удалить из корпуса, если ячейка пуста. Для этого необходимо зажать Shift и кликнуть ПКМ, держа в руках саму ячейку.

## Емкость хранения с различным количеством типов

[Первоначальная стоимость типов](../ae2-mechanics/bytes-and-types.md) такова, что ячейка, содержащая 1 тип, может вместить в 2 раза больше, чем ячейка, в которой используются все 63 типа.

| Ячейка                                   | Общая емкость ячейки с 1 использ. типом   | Общая емкость ячейки с 63 типами в использ. |
| ---------------------------------------- | ----------------------------------------: | ------------------------------------------: |
| <ItemLink id="item_storage_cell_1k" />   |                                     8,128 |                                       4,160 |
| <ItemLink id="item_storage_cell_4k" />   |                                    32,512 |                                      16,640 |
| <ItemLink id="item_storage_cell_16k" />  |                                   130,048 |                                      66,560 |
| <ItemLink id="item_storage_cell_64k" />  |                                   520,192 |                                     266,240 |
| <ItemLink id="item_storage_cell_256k" /> |                                 2,080,768 |                                   1,064,960 |


## Разбитие на разделы

Ячейки можно фильтровать, чтобы они принимали только определенные предметы, аналогично тому, как можно фильтровать <ItemLink id="storage_bus" />. Это
делается в <ItemLink id="cell_workbench" />.

Предметы можно перетаскивать в слоты из JEI/REI, даже если у вас на самом деле нет ни одного такого предмета.

## Улучшения

Ячейки хранения поддерживают следующие [улучшения](upgrade_cards.md), вставленные через <ItemLink id="cell_workbench" />:

*   <ItemLink id="fuzzy_card" /> (недоступно на жидких ячейках) позволяет разделить ячейку по уровню повреждения и/или игнорировать NBT элемента.
*   <ItemLink id="inverter_card" /> переключает фильтр с белого списка на черный список.
*   <ItemLink id="equal_distribution_card" /> распределяет одинаковое количество байтового пространства ячейки для каждого типа, поэтому один тип не может заполнить всю ячейку.
*   <ItemLink id="void_card" /> аннулирует вставленные элементы, если ячейка заполнена (или выделенное место для этого конкретного типа в случае карты равномерного распределения), полезно для предотвращения заполнения хранилищ ферм. Будьте осторожны при разбиении на разделы!
*   Переносные ячейки могут принимать <ItemLink id="energy_card" /> для увеличения емкости аккумулятора.

## Окрашивание

Переносные предметные и жидкостные ячейки хранения можно окрашивать так же, как кожаную броню, создавая их вместе с красителями.

# Корпуса

Ячейки могут быть изготовлены с компонентом хранения и корпусом или с рецептом изготовления корпуса вокруг компонента хранения:

<Row>
  <Recipe id="network/cells/item_storage_cell_1k" />

  <Recipe id="network/cells/item_storage_cell_1k_storage" />
</Row>

Сами корпуса изготавливаются следующим образом:

<Row>
  <RecipeFor id="item_cell_housing" />

  <RecipeFor id="fluid_cell_housing" />
</Row>

# Компоненты хранения

Компоненты хранения являются ядром всех ячеек AE2, определяя ёмкость ячеек. Каждый уровень увеличивает ёмкость в 4 раза и стоит 3 компонента предыдущих уровня.

<Column>
  <Row>
    <RecipeFor id="cell_component_1k" />

    <RecipeFor id="cell_component_4k" />

    <RecipeFor id="cell_component_16k" />
  </Row>

  <Row>
    <RecipeFor id="cell_component_64k" />

    <RecipeFor id="cell_component_256k" />
  </Row>
</Column>

# Предметные ячейки хранения

Предметные ячейки хранения могут содержать до 63 различных типов предметов и доступны во всех стандартных емкостях.

<Column>
  <Row>
    <Recipe id="network/cells/item_storage_cell_1k_storage" />

    <Recipe id="network/cells/item_storage_cell_4k_storage" />

    <Recipe id="network/cells/item_storage_cell_16k_storage" />
  </Row>

  <Row>
    <Recipe id="network/cells/item_storage_cell_64k_storage" />

    <Recipe id="network/cells/item_storage_cell_256k_storage" />
  </Row>
</Column>

## Переносные предметные ячейки хранения

Они действуют как крошечный <ItemLink id="chest" /> в вашем кармане или как своего рода рюкзак. Их можно заряжать в <ItemLink id="charger" />.

В отличие от стандартных ячеек хранения, эти ячейки фактически *уменьшают* ёмкость в типах по мере увеличения ёмкости в байтах и имеют половину общей емкости в байтах.

В дополнение к картам улучшений, которые могут получить все ячейки, они также принимают <ItemLink id="energy_card" /> для улучшения своих внутренних аккумуляторов.

<Column>
  <Row>
    <RecipeFor id="portable_item_cell_1k" />

    <RecipeFor id="portable_item_cell_4k" />

    <RecipeFor id="portable_item_cell_16k" />
  </Row>

  <Row>
    <RecipeFor id="portable_item_cell_64k" />

    <RecipeFor id="portable_item_cell_256k" />
  </Row>
</Column>

# Жидкостные ячейки хранения

Жидкостные ячейки хранения могут содержать до 5 различных типов жидкостей и доступны во всех стандартных объемах.

<Column>
  <Row>
    <Recipe id="network/cells/fluid_storage_cell_1k_storage" />

    <Recipe id="network/cells/fluid_storage_cell_4k_storage" />

    <Recipe id="network/cells/fluid_storage_cell_16k_storage" />
  </Row>

  <Row>
    <Recipe id="network/cells/fluid_storage_cell_64k_storage" />

    <Recipe id="network/cells/fluid_storage_cell_256k_storage" />
  </Row>
</Column>

## Перененосные жидкостные ячейки хранения

Они действуют как крошечный <ItemLink id="chest" /> в вашем кармане или как своего рода рюкзак. Их можно заряжать в <ItemLink id="charger" />.

В отличие от стандартных ячеек хранения, эти ячейки фактически *уменьшают* ёмкость в типах по мере увеличения ёмкости в байтах и имеют половину общей емкости в байтах.

В дополнение к картам улучшений, которые могут получить все ячейки, они также принимают <ItemLink id="energy_card" /> для улучшения своих внутренних аккумуляторов.

<Column>
  <Row>
    <RecipeFor id="portable_fluid_cell_1k" />

    <RecipeFor id="portable_fluid_cell_4k" />

    <RecipeFor id="portable_fluid_cell_16k" />
  </Row>

  <Row>
    <RecipeFor id="portable_fluid_cell_64k" />

    <RecipeFor id="portable_fluid_cell_256k" />
  </Row>
</Column>

# Творческие предметные и жидкостные ячейки хранения

<Row>
  <ItemImage id="creative_item_cell" scale="2" />

  <ItemImage id="creative_fluid_cell" scale="2" />
</Row>

Творческие предметные и жидкостные ячейки хранения **не обеспечивают бесконечное хранение**. Вместо этого, они действуют как бесконечные источники и поглотители любого предмета или жидкости, которые вы [разделяете](cell_workbench.md) на них.
