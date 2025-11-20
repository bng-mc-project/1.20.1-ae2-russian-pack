---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Кабели
  icon: fluix_glass_cable
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:white_glass_cable
- ae2:orange_glass_cable
- ae2:magenta_glass_cable
- ae2:light_blue_glass_cable
- ae2:yellow_glass_cable
- ae2:lime_glass_cable
- ae2:pink_glass_cable
- ae2:gray_glass_cable
- ae2:light_gray_glass_cable
- ae2:cyan_glass_cable
- ae2:purple_glass_cable
- ae2:blue_glass_cable
- ae2:brown_glass_cable
- ae2:green_glass_cable
- ae2:red_glass_cable
- ae2:black_glass_cable
- ae2:fluix_glass_cable
- ae2:white_covered_cable
- ae2:orange_covered_cable
- ae2:magenta_covered_cable
- ae2:light_blue_covered_cable
- ae2:yellow_covered_cable
- ae2:lime_covered_cable
- ae2:pink_covered_cable
- ae2:gray_covered_cable
- ae2:light_gray_covered_cable
- ae2:cyan_covered_cable
- ae2:purple_covered_cable
- ae2:blue_covered_cable
- ae2:brown_covered_cable
- ae2:green_covered_cable
- ae2:red_covered_cable
- ae2:black_covered_cable
- ae2:fluix_covered_cable
- ae2:white_covered_dense_cable
- ae2:orange_covered_dense_cable
- ae2:magenta_covered_dense_cable
- ae2:light_blue_covered_dense_cable
- ae2:yellow_covered_dense_cable
- ae2:lime_covered_dense_cable
- ae2:pink_covered_dense_cable
- ae2:gray_covered_dense_cable
- ae2:light_gray_covered_dense_cable
- ae2:cyan_covered_dense_cable
- ae2:purple_covered_dense_cable
- ae2:blue_covered_dense_cable
- ae2:brown_covered_dense_cable
- ae2:green_covered_dense_cable
- ae2:red_covered_dense_cable
- ae2:black_covered_dense_cable
- ae2:fluix_covered_dense_cable
- ae2:white_smart_cable
- ae2:orange_smart_cable
- ae2:magenta_smart_cable
- ae2:light_blue_smart_cable
- ae2:yellow_smart_cable
- ae2:lime_smart_cable
- ae2:pink_smart_cable
- ae2:gray_smart_cable
- ae2:light_gray_smart_cable
- ae2:cyan_smart_cable
- ae2:purple_smart_cable
- ae2:blue_smart_cable
- ae2:brown_smart_cable
- ae2:green_smart_cable
- ae2:red_smart_cable
- ae2:black_smart_cable
- ae2:fluix_smart_cable
- ae2:white_smart_dense_cable
- ae2:orange_smart_dense_cable
- ae2:magenta_smart_dense_cable
- ae2:light_blue_smart_dense_cable
- ae2:yellow_smart_dense_cable
- ae2:lime_smart_dense_cable
- ae2:pink_smart_dense_cable
- ae2:gray_smart_dense_cable
- ae2:light_gray_smart_dense_cable
- ae2:cyan_smart_dense_cable
- ae2:purple_smart_dense_cable
- ae2:blue_smart_dense_cable
- ae2:brown_smart_dense_cable
- ae2:green_smart_dense_cable
- ae2:red_smart_dense_cable
- ae2:black_smart_dense_cable
- ae2:fluix_smart_dense_cable
---

# Кабели

<GameScene zoom="3" background="transparent">
  <ImportStructure src="../assets/assemblies/cables.snbt" />
  <IsometricCamera yaw="180" pitch="30" />
</GameScene>

Хотя сети ME также создаются соседними машинами, поддерживающими ME, кабели являются основным способом расширения сети ME на большие площади.

Кабели разного цвета можно использовать для того, чтобы соседние кабели не соединялись друг с другом,
что позволяет более эффективно распределять [каналы](../ae2-mechanics/channels.md). Они также влияют на цвет подключенных к ним терминалов, поэтому вам не нужно, чтобы все ваши терминалы были фиолетовыми. Флюисовые кабели подключаются к любому другому цвету.

Обратите внимание, что **КАНАЛЫ НЕ ИМЕЮТ НИКАКОГО ОТНОШЕНИЯ К ЦВЕТУ КАБЕЛЯ**.

## Важная заметка

**Если вы новичок в AE2 и не знакомы с каналами, используйте умный кабель и плотный умный кабель везде, где это возможно. Это покажет, как каналы проходят через вашу сеть, что сделает их поведение более понятным.**

## Другая заметка

**Это не трубы для предметов, жидкостей, энергии и т. д.** Они не имеют внутреннего инвентаря, поставщики шаблонов и машины не «толкают/перемещают» в них, все, что они делают, — это соединяют AE2 [устройства](../ae2-mechanics/devices.md) в сеть.

## Стеклянный кабель

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/fluix_glass_cable.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

<ItemLink id="fluix_glass_cable" /> — это самый простой в изготовлении кабель, который передает энергию и до 8 [каналов](../ae2-mechanics/channels.md). Он доступен в 17 различных цветах, по умолчанию — флюисовый, и может быть окрашен в любой цвет с помощью любого из 16 красителей.

Чтобы изготовить цветные кабели, окружите краситель любого типа 8 кабелями одного типа (цвет кабелей не имеет значения, но они должны быть одного типа: стеклянные, умные и т. д.).

Вы можете убрать краситель с кабеля, если поместите покрашенный кабель и ведро с водой в верстаке (или в любой сетке крафта)

Вы можете покрыть кабель шерстью, чтобы создать <ItemLink id="fluix_covered_cable" />, и изготовить <ItemLink id="fluix_smart_cable" />, чтобы лучше понять, что происходит с вашими [каналами](../ae2-mechanics/channels.md).

<RecipeFor id="fluix_glass_cable" />

<RecipeFor id="blue_glass_cable" />

## Покрытый кабель

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_covered_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Вариант с покрытым кабелем не дает никаких преимуществ в игровом процессе по сравнению с его аналогом <ItemLink id="fluix_glass_cable" />. Однако его можно использовать в качестве альтернативного эстетического решения, если вам больше нравится покрытый вид.

Может быть окрашен таким же образом, как <ItemLink id="fluix_glass_cable" />. Чтобы изготовить <ItemLink id="fluix_covered_dense_cable" /> необходимо совместить 4 <ItemLink id="fluix_covered_cable" /> с редстоуновой пылью и светокаменной пылью.

<Recipe id="network/cables/covered_fluix" />

<RecipeFor id="blue_covered_cable" />

## Непрозрачный кабель

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_covered_dense_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Кабель с более высокой пропускной способностью, может передавать 32 канала, в отличие от стандартного кабеля, который может передавать только 8, однако он не поддерживает шины, поэтому перед использованием шин или панелей необходимо сначала перейти с непрозрачного кабеля на кабель меньшего размера (например, <ItemLink id="fluix_glass_cable" /> или <ItemLink id="fluix_smart_cable" />).

Непрозрачные кабели слегка перекрывают поведение каналов по принципу «кратчайшего пути»: каналы выбирают кратчайший путь к непрозрачному кабелю, а затем кратчайший путь через этот непрозрачный кабель к контроллеру.

<Recipe id="network/cables/dense_covered_fluix" />

<RecipeFor id="blue_covered_dense_cable" />

## Умный кабель

<Row>
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_smart_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_smart_dense_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>
</Row>

Несмотря на некоторое внешнее сходство с <ItemLink id="fluix_covered_cable" />, они обеспечивают диагностическую функцию, визуализируя использование каналов на кабелях. Каналы отображаются в виде цветных линий, проходящих вдоль черной полосы на кабелях, что позволяет понять, как используются каналы в вашей сети. Для обычных умных кабелей первые четыре канала отображаются в виде линий, соответствующих цвету кабеля, а следующие четыре — в виде белых линий. Для непрозрачных умных кабелей каждая полоса представляет 4 канала.

В сетях с <ItemLink id="controller" /> линии на кабелях показывают точный путь, по которому проходят каналы.

Умные кабели в "неполноценных" сетях будут отображать количество каналов, используемых в сети, а не количество каналов, проходящих через конкретный кабель.

Их также можно раскрасить таким же образом, как <ItemLink id="fluix_glass_cable" />.

<Recipe id="network/cables/smart_fluix" />

<Recipe id="network/cables/dense_smart_fluix" />

<RecipeFor id="blue_smart_cable" />
