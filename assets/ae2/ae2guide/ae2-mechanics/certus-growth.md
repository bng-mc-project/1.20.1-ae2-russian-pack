---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Рост сертус-кварца
  icon: quartz_cluster
---

# Рост сертус-кварца

## По сути просто копипаста со страницы для начинающих

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/budding_certus_1.snbt" />
</GameScene>

Почки сертус-кварца будут прорастать из [блоков растущего сертуса](../items-blocks-machines/budding_certus.md), подобно аметисту. Если вы сломаете почку, которая ещё не выросла, она выпадет в виде одного <ItemLink id="certus_quartz_dust" />, и этот результат не изменяется под действием удачи (Fortune). Если вы сломаете полностью выросший кластер, он выпадет в виде четырёх <ItemLink id="certus_quartz_crystal" />, и удача увеличит это количество.

Существует 4 уровня блоков растущего сертуса: Безупречный, С изъяном, Сколотый и Повреждённый.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/budding_blocks.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Каждый раз, когда почка переходит на следующую стадию роста, блок растущего сертуса имеет шанс деградировать на один уровень, в конечном итоге превращаясь в обычный блок сертус-кварца. Их можно починить (или создать новые блоки растущего сертуса), бросив блок (или обычный блок сертус-кварца) в воду вместе с одним или несколькими <ItemLink id="charged_certus_quartz_crystal" />.

<RecipeFor id="damaged_budding_quartz" />

Безупречные блоки растущего сертуса не деградируют и будут бесконечно генерировать сертус. Однако их нельзя создать или переместить киркой, даже с шелковым касанием (Silk Touch). (Но их *можно* переместить с помощью [пространственного хранилища](../ae2-mechanics/spatial-io.md)).

Самостоятельно почки сертус-кварца растут очень медленно. К счастью, <ItemLink id="growth_accelerator" /> значительно ускоряет этот процесс, если разместить его рядом с блоком растущего сертуса. Вам следует построить несколько таких устройств в первую очередь.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/budding_certus_2.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Если у вас недостаточно кварца для создания <ItemLink id="energy_acceptor" /> или <ItemLink id="vibration_chamber" />, вы можете сделать <ItemLink id="crank" /> и прикрепить его к ускорителю.

Автоматический сбор сертуса [описан здесь](../example-setups/simple-certus-farm.md).