---
navigation:
  parent: example-setups/example-setups-index.md
  title: Авто-пополнение интерфейса
  icon: interface
---

# Авто-пополнение интерфейса

Вы можете спросить: "Как мне поддерживать определенное количество различных предметов на складе и изготавливать дополнительные по мере необходимости?"

Одним из решений является использование <ItemLink id="interface" /> и <ItemLink id="crafting_card" /> для автоматического запроса новых предметов
из установки [автоматического крафта](../ae2-mechanics/autocrafting.md) вашей сети. Эта установка больше подходит для поддержания небольшого количества широкого
разнообразия предметов.

Эта демонстрационная установка укорочена, чтобы не быть слишком широкой, вероятно, наиболее оптимальным будет использовать 4 <ItemLink id="interface" /> и 4 <ItemLink id="storage_bus" />,
чтобы использовать все 8 [канала](../ae2-mechanics/channels.md) в обычном [кабеле](../items-blocks-machines/cables.md).

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/interface_autostocking.snbt" />

<BoxAnnotation color="#dddddd" min="0 0 0" max="2 1 1">
        (1) Интерфейсы: настроены так, чтобы сохранять нужные предметы в себе. Имеют карты изготовления.
        <ItemImage id="crafting_card" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 0" max="2 1.3 1">
        (2) Шины хранения: "Режим ввода/вывода" установлен на "Только извлечение".
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        To Main Network
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Настройки

* <ItemLink id="interface" /> (1) настроены так, чтобы сохранять нужные предметы в себе, для чего нужно щелкнуть нужный предмет в их
   верхних слотах или перетащить его в верхние слоты из JEI, а затем щелкнуть на значок гаечного ключа над слотами, чтобы установить количество. Они имеют <ItemLink id="crafting_card" />.
* <ItemLink id="storage_bus" /> (2) настроены таким образом, что "Режим ввода/вывода" установлен на "Только извлечение".

## Как это работает

1. Если <ItemLink id="interface" /> не может получить достаточное количество настроенных предметов из [сетевого хранилища](../ae2-mechanics/import-export-storage.md),
   (и у него есть <ItemLink id="crafting_card" />), он запросит, чтобы установка [автоматического крафта](../ae2-mechanics/autocrafting.md) сети изготовила больше этих предметов.
2. <ItemLink id="storage_bus" /> позволяют сети получить доступ к содержимому интерфейсов.