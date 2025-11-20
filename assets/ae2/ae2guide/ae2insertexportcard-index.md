---
navigation:
  title: "Дополнение: AE2 Карты вставки и экспорта"
  icon: ae2insertexportcard:export_card
  position: 150
categories:
  - tools
item_ids:
- ae2insertexportcard:export_card
- ae2insertexportcard:insert_card
---

# AE2 Карты вставки и экспорта

<Row>
  <ItemImage id="ae2insertexportcard:export_card" scale="2" />

  <ItemImage id="ae2insertexportcard:insert_card" scale="2" />
</Row>

Карты «Вставка» и «Экспорт» позволяют вам вставлять/экспортировать предметы в/из вашего инвентаря.

## Insert Card

<ItemImage id="ae2insertexportcard:insert_card" scale="2" />

Карта вставки берет предметы из определенных слотов вашего инвентаря и сбрасывает их в вашу систему МЭ.

![Insert Card](diagrams/insert_card.png)

При нажатии на слот появляется галочка. Любой предмет в слоте, отмеченный галочкой, будет импортирован в вашу систему ME. Перетащите предметы из инвентаря наверх, чтобы изменить фильтр.

### Улучшения

Вставная карта поддерживает следующие: [улучшения](items-blocks-machines/upgrade_cards.md):

*   <ItemLink id="fuzzy_card" /> фильтр по уровню повреждения и/или игнорировать элемент NBT
*   <ItemLink id="inverter_card" /> переключает фильтр из белого списка в черный список

### Рецепт

<RecipeFor id="ae2insertexportcard:insert_card" />

## Export Card

<ItemImage id="ae2insertexportcard:export_card" scale="2" />

Карта экспорта работает точно так же, но переносит предметы из вашей системы ME в ваш инвентарь.

![Карта экспорта](diagrams/export_card.png)

Чтобы указать предметы, перетащите предмет из инвентаря в один из слотов вверху и нажмите на слот в инвентаре, чтобы изменить его номер на нужный. Щелчок правой кнопкой мыши очистит слот, вернув его к полю X.

### Улучшения

Экспортная карта поддерживает следующие [улучшения](items-blocks-machines/upgrade_cards.md):

*   <ItemLink id="fuzzy_card" /> фильтр по уровню повреждения и/или игнорировать элемент NBT
*   <ItemLink id="speed_card" /> увеличивает скорость передачи от 1 до целой стопки предметов
*   <ItemLink id="crafting_card" /> автоматически запрашивает и создаёт предметы, которые в данный момент недоступны в сети

### Рецепт

<RecipeFor id="ae2insertexportcard:export_card" />