---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Сетевые подключения
  icon: fluix_glass_cable
---

# Сетевые подключения

## Что такое "Сеть"?

"Сеть" — это группа [устройств](../ae2-mechanics/devices.md), соединённых блоками, которые могут передавать [каналы](../ae2-mechanics/channels.md), такие как [кабели](../items-blocks-machines/cables.md) или полноразмерные машины и [устройства](../ae2-mechanics/devices.md). 
(<ItemLink id="charger" />, <ItemLink id="interface" />, <ItemLink id="drive" /> и т.д.)
Технически, даже один кабель уже является сетью.

## Замечание о расположении устройств

Для [устройств](../ae2-mechanics/devices.md), выполняющих определённые сетевые функции (например, <ItemLink id="interface" />, взаимодействующий с [сетевым хранилищем](../ae2-mechanics/import-export-storage.md), или <ItemLink id="level_emitter" />, читающий содержимое хранилища), физическое расположение устройства не имеет значения.

Повторюсь: **физическое расположение устройства не имеет значения**. Важно только, что устройство подключено к сети (и, конечно, к какой именно сети).

## Подключение сетей

Простой способ определить, что подключено к сети — использовать <ItemLink id="network_tool" />. Он покажет все компоненты сети, поэтому если вы видите лишнее или не видите нужное, у вас проблема.

Например, это две отдельные сети:

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

Это тоже две отдельные сети, потому что <ItemLink id="quartz_fiber" /> передаёт [энергию](../ae2-mechanics/energy.md), но не обеспечивает сетевое подключение.

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

Однако это одна сеть, а не две. [Квантовый мост](../items-blocks-machines/quantum_bridge.md) действует как беспроводной [плотный кабель](../items-blocks-machines/cables.md#dense-cable), поэтому оба конца принадлежат одной сети.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/actually_1_network.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="7 3 3">
        Одна сеть
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Это тоже одна сеть, так как [цвет кабеля](../items-blocks-machines/cables.md) не влияет на подключение, кроме случаев, когда кабели разных цветов не соединяются друг с другом. Все цвета соединяются с кабелями fluix (или "бесцветными").

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/actually_1_network_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        Одна сеть
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Менее очевидные подключения

В этом случае это одна сеть, потому что <ItemLink id="pattern_provider" />, будучи полноразмерным устройством, действует как кабель, и <ItemLink id="inscriber" /> ведёт себя аналогично. Таким образом, сетевое подключение проходит через поставщика шаблонов и инскрайбер.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_network_connection_1.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        Одна сеть
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Чтобы предотвратить это (что полезно для многих систем автокрафта с [подсетями](../ae2-mechanics/subnetworks.md)), можно нажать ПКМ на поставщика шаблонов с <ItemLink id="certus_quartz_wrench" />, чтобы сделать его направленным — тогда он не будет передавать каналы через одну из сторон.

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

Другие части, которые не обеспечивают направленных сетевых подключений — это большинство [подчастей](../ae2-mechanics/cable-subparts.md) [устройств](../ae2-mechanics/devices.md), таких как <ItemLink id="import_bus" />, <ItemLink id="storage_bus" /> и <ItemLink id="cable_interface" />.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/subpart_no_connection.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>