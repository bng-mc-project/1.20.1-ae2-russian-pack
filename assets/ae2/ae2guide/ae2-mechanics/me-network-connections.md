---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Сетевые подключения
  icon: fluix_glass_cable
---

# Сетевые подключения

## Что означает «сеть»?

«Сеть» — это группа [устройств](../ae2-mechanics/devices.md), подключённые блоками, которые могут передавать [каналы](../ae2-mechanics/channels.md),
такими как [кабели](../items-blocks-machines/cables.md) или полноблочные машины и [устройства](../ae2-mechanics/devices.md). 
(<ItemLink id="charger" />, <ItemLink id="interface" />, <ItemLink id="drive" /> и т. д.)
Технически, один кабель — это сеть. 

## Отступление о расположении устройств

Для [устройств](../ae2-mechanics/devices.md), которые имеют определенные сетевые функции (например, <ItemLink id="interface" />
передача данных в [сетевое хранилище](../ae2-mechanics/import-export-storage.md) и извлечение данных из него, <ItemLink id="level_emitter" />
чтение содержимого сетевого хранилища, <ItemLink id="drive" /> являющееся сетевым хранилищем и т. д.)
физическое расположение устройства не имеет значения.

Опять же, **физическое расположение устройства не имеет значения**. Важно только то, что устройство подключено к сети
(и, конечно, к какой именно сети).

## Сетевые подключения

Простой способ определить, что подключено к сети, — использовать <ItemLink id="network_tool" />. Он покажет все
компоненты в сети, поэтому, если вы видите то, чего не должны, или не видите то, что должны, у вас есть проблема.

Например, это 2 отдельных сети.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/2_networks_1.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1 2 2">
        Сеть 1
  </BoxAnnotation>

<BoxAnnotation color="#915dcd" min="2 0 0" max="3 2 2">
        Сеть 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Это также 2 отдельных сети, потому что <ItemLink id="quartz_fiber" /> делится [энергией](../ae2-mechanics/energy.md),
 не обеспечивая сетевого соединения.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/2_networks_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1 2 2">
        Сеть 1
  </BoxAnnotation>

  <BoxAnnotation color="#915dcd" min="1.3 0 0" max="3 2 2">
        Сеть 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Однако это всего лишь 1 сеть, а не 2 отдельных. [Квантовый мост](../items-blocks-machines/quantum_bridge.md) действует как
беспроводной [непрозрачный кабель](../items-blocks-machines/cables.md#dense-cable), поэтому оба конца находятся в одной сети.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/actually_1_network.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="7 3 3">
        Всё это 1 сеть
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Это также всего лишь 1 сеть, так как цвет [кабеля](../items-blocks-machines/cables.md) не имеет ничего общего с сетевыми соединениями, кроме того, что кабели разных цветов не
соединяются друг с другом. Все цвета соединяются с флюисовыми кабелями (или «бесцветными»).

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/actually_1_network_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        Все это 1 сеть
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Менее интуитивные связи

В данном случае это всего лишь 1 сеть, поскольку <ItemLink id="pattern_provider" />, являясь устройством полного блока, действует как
кабель, а <ItemLink id="inscriber" /> выполняет аналогичную функцию. Таким образом, сетевое соединение проходит через
поставщика и вырезателя.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_network_connection_1.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        Всё это 1 сеть
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Чтобы этого избежать (что полезно для многих установок автоматического крафта, включающих [подсети](../ae2-mechanics/subnetworks.md)),
вы можете щелкнуть правой кнопкой мыши по поставщику с <ItemLink id="certus_quartz_wrench" />, чтобы сделать его направленным, и в этом случае он
не будет пропускать каналы через одну сторону.

<Row gap="40">
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_network_connection_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="2 2 2">
        Сеть 1
  </BoxAnnotation>

  <BoxAnnotation color="#915dcd" min="2 0 0" max="4 2 2">
        Сеть 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_directional_connection.snbt" />

  <BoxAnnotation color="#ee3333" min="1 .3 .3" max="1.3 .7 .7">
        Обратите внимание, что кабель не соединяется

  </BoxAnnotation>

  <IsometricCamera yaw="255" pitch="30" />
</GameScene>
</Row>

Другие детали, которые не обеспечивают направленные сетевые соединения, в основном являются [подразделами](../ae2-mechanics/cable-subparts.md)
[устройствами](../ae2-mechanics/devices.md), такими как <ItemLink id="import_bus" />, <ItemLink id="storage_bus" /> и
<ItemLink id="cable_interface" />.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/subpart_no_connection.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>