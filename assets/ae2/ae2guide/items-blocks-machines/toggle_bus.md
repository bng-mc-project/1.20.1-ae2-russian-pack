---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Шина переключения
  icon: toggle_bus
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:toggle_bus
- ae2:inverted_toggle_bus
---

# Шина переключения

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/assemblies/toggle_bus.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

Шина, которая функционирует похоже на <ItemLink id="fluix_glass_cable" /> или на другие кабели. но позволяет контролировать состояние соединения, путём переключения через редстоун. Это позволяет вам отрезать определённые секции [МЭ сети](../ae2-mechanics/me-network-connections.md).

Когда к шине подключен редстоун сигнал, то соединение не предотвращается, <ItemLink id="inverted_toggle_bus" /> имеет же противоположное поведение, при подаче сигнала он предотвращает соединение.

Обратите внимание, переключение может привести к перезапуску сети или перерасчёту подключённых устройств.

Шина переключения является [подразделом кабеля](../ae2-mechanics/cable-subparts.md).

## Рецепты

<RecipeFor id="toggle_bus" />

<RecipeFor id="inverted_toggle_bus" />
