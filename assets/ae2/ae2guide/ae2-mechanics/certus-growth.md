---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Выращивание истинного кварца
  icon: quartz_cluster
---

# Выращивание истинного кварца

## Просто скопировано со страницы "Начало"

<GameScene zoom="4" background="transparent">
<ImportStructure src="../assets/assemblies/budding_certus_1.snbt" />
</GameScene>

Бутоны истинного кварца растут со [цветущих блоков истинного кварца](../items-blocks-machines/budding_certus.md), это похоже на то, как растёт аметист. Если вы сломаете бутон до того как тот вырастет до конца, тогда выпадет 1 <ItemLink id="certus_quartz_dust" />, зачарование "Удачи" не изменяет количество. Если же вы сломаете полностью вырасшую друзу, тогда выпадет 4 <ItemLink id="certus_quartz_crystal" /> и уже их количество может быть увеличено с помощью Удачи

Вот все 4 уровня цветущего блока истинного кварца: Безупречный, Потресканный/Несовершенный, Потресканный/Сколотый, Повреждённый.

<GameScene zoom="4" background="transparent">
<ImportStructure src="../assets/assemblies/budding_blocks.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

Каждый раз когда бутон вырастает до другой стадии, цветущий блок имеет шанс деградировать на 1 уровень, что по тихоньку превращает его в обычный блок истинного кварца. Цветущий блок может быть починен (и новый цветущий блок может быть создан) при кидании цветущего блока (или блока истинного кварца) в воду с одним или более <ItemLink id="charged_certus_quartz_crystal" />.

<RecipeFor id="damaged_budding_quartz" />

Безупречный цветущий блок истинного кварца не будет деградировать и будет генерировать истинный кварц вечно. Однако этот блок не может быть создан или перемещён с помощью кирки, даже если на ней есть Шёлковое касание (но блок *может* быть перемещён с помощью [пространственного хранилища](../ae2-mechanics/spatial-io.md))

Самостоятельно бутоны истинного кварца растут крайне медленно. К счастью, <ItemLink id="growth_accelerator" /> значительно ускоряет данный процесс, если поставлен вплотную к цветущиму блоку. Вам следует построить несколько из них в первую очередь.

<GameScene zoom="4" background="transparent">
<ImportStructure src="../assets/assemblies/budding_certus_2.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

Если у вас не хватает кварца, чтобы сделать <ItemLink id="energy_acceptor" /> или <ItemLink id="vibration_chamber" />,
то тогда вы можете сделать <ItemLink id="crank" /> и поставить его на нужный ускоритель

Автоматическая добыча истинного кварца [описана здесь](../example-setups/simple-certus-farm.md).