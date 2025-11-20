---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Зарядник
  icon: charger
  position: 310
categories:
- machines
item_ids:
- ae2:charger
---

# Зарядник

<BlockImage id="charger" scale="8" />

Зарядник позволяет заряжать поддерживаемые инструменты и <ItemLink id="certus_quartz_crystal" />.

Энергия может быть подана через верхнюю или нижнюю часть, с помощью любых AE2 [кабелей](cables.md) или любых кабелей для передачи энергии из других модов. Может принимать как AE2 Энергию (AE), так и Forge Energy (FE). Предметы могут быть вставлены или вытащены с любой стороны. Однако, лишь результаты могут быть вытащены, поэтому вам не придётся ставить фильтры для предотвращения случайного изымания кристаллов истинного кварца, вместо заряженных кристаллов истинного кварца. Может быть повёрнут с помощью <ItemLink id="certus_quartz_wrench" /> для облегчения автоматизации.

Может быть использован для изготовления <ItemLink id="charged_certus_quartz_crystal" /> из <ItemLink id="certus_quartz_crystal" /> и <ItemLink id="meteorite_compass" /> из <ItemLink id="minecraft:compass" />.

Для питания его в ручном режиме, расположите <ItemLink id="crank" /> на верхней или нижней части и удерживайте ПКМ пока предмет не зарядится.

Оно также является рабочим местом для AE2 жителя.

## Простая автоматизация

Как пример, возможность лёгкого поворота позволяет полу-автоматизировать зарядники. К примеру так:

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/charger_hopper.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Рецепт

<RecipeFor id="charger" />
