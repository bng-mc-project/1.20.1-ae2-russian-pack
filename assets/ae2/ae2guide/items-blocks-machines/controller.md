---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Контроллер МЭ сети
  icon: controller
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:controller
---

# Контроллер МЭ сети

<BlockImage id="controller" p:state="online" scale="8" />

Контроллер МЭ сети это основопологающая часть [МЭ сети](../ae2-mechanics/me-network-connections.md), можно сказать её сердце.
Без неё, сеть по сути "не полноценная", у неё всего может быть лишь 8 использующих каналы [устройств](../ae2-mechanics/devices.md).

Невозможно, чтобы было 2 контроллера МЭ сети в одной [МЭ сети](../ae2-mechanics/me-network-connections.md).

Контроллер предоставляет 32 [канала](../ae2-mechanics/channels.md) на каждую грань.

Контроллер МЭ сети требует 6 AE/t за каждый МЭ-регулятор, чтобы функционировать. Каждый МЭ-регулятор может хранить 8000 AE, так что для больших сетей вам необходимы дополнительный хранилища энегрии. Посмотрите статью ["Энергия"](../ae2-mechanics/energy.md) для уточнения.

Мультиблочные МЭ-регуляторы могут быть построены в довольно разнообразных формах.

<GameScene zoom="2" background="transparent">
  <ImportStructure src="../assets/assemblies/controllers.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Однако, существуют несколько правил, которые должны быть соблюдены:

1. Все МЭ-регуляторы в [МЭ сети](../ae2-mechanics/me-network-connections.md) должны быть подключены; иначе блоки будут  красными.
2.  Размер контроллера МЭ сети должен быть менее 7х7х7; иначе блоки будут красными.
3.  МЭ-регулятор может иметь 2 смежных блока максимум по 1 оси; если блок нарушает это правило, он отключается и становится красным.

<GameScene zoom="2" background="transparent">
  <ImportStructure src="../assets/assemblies/controller_rules.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

До тех пор пока все правила соблюдены и контроллер МЭ сети запитан, он будет светится и циклично изменять цвета

Вы можете кликнуть ПКМ по контроллеру МЭ сети, чтобы получить такое же GUI как у <ItemLink id="network_tool" />

## Рецепт

<RecipeFor id="controller" />
