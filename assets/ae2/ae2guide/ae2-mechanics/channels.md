---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Каналы
  icon: controller
---

# Каналы

Для [MЭ сети](me-network-connections.md) Applied Energistics 2 требуются
каналы для поддержки [устройств](../ae2-mechanics/devices.md), которые используют сетевое хранилище или другую сеть.
Представьте себе каналы как USB-кабели для всех ваших устройств. Компьютер имеет ограниченное количество USB-портов и может поддерживать только то количество устройств, сколько существует USB-портов. Большинство машин, полноблочных устройств и стандартных кабелей могут пропускать только
до 8 каналов. Полноблочные устройства и стандартные кабели можно представить как связку из 8 "канальных кабелей". Однако [непрозрачные кабели](../items-blocks-machines/cables.md#dense-cable) могут поддерживать до
до 32 каналов. Единственные другие кабеля, способные передавать 32 канала, — это <ItemLink id="me_p2p_tunnel" />
и [Квантовый сетевой мост](../items-blocks-machines/quantum_bridge.md). Каждый раз, когда устройство использует канал, представьте, что вы отсоединяете USB-кабель от
пучка, что, очевидно, означает, что "кабель" далее по линии недоступен.

<GameScene zoom="7" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_demonstration_1.snbt" />

  <LineAnnotation color="#33ff33" from="1 .4 .7" to="2.4 .4 .7" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .6 .7" to="2.4 .6 .7" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .4 .6" to="2.6 .4 .6" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .6 .6" to="2.6 .6 .6" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .6 .6" to="2.6 .6 .6" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="2.4 .6 .7" to="2.4 .6 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.4 .4 .7" to="2.4 .4 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.6 .6 .6" to="2.6 .6 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.6 .4 .6" to="2.6 .4 1.5" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="2.1 .6 1.5" to="2.4 .6 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.6 .4 1.5" to="2.9 .4 1.5" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="2.6 .6 1.5" to="2.6 .9 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.4 .1 1.5" to="2.4 .4 1.5" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="1 .6 .4" to="3.5 .6 .4" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .4 .4" to="3.5 .4 .4" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="3.5 .6 .4" to="3.5 .9 .4" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="3.5 .1 .4" to="3.5 .4 .4" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="1 .6 .3" to="1.5 .6 .3" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .4 .3" to="1.5 .4 .3" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="1.5 .6 .3" to="1.5 .9 .3" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1.5 .1 .3" to="1.5 .4 .3" alwaysOnTop={true}/>

  <LineAnnotation color="#ff3333" from="3.5 .5 .5" to="5.5 .5 .5" alwaysOnTop={true}>
  Все 8 каналов в кабелей используются, поэтому Дисковод не может получить ни одного.
  </LineAnnotation>

  <LineAnnotation color="#993333" from="1 .5 .5" to="1.25 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="1.5 .5 .5" to="1.75 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="2 .5 .5" to="2.25 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="2.5 .5 .5" to="2.75 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="3 .5 .5" to="3.25 .5 .5" alwaysOnTop={true}/>

  <DiamondAnnotation pos="3.6 0.5 0.5" color="#ff0000">
        Все 8 каналов в кабелей используются, поэтому Дисковод не может получить ни одного.
    </DiamondAnnotation>

  <IsometricCamera yaw="15" pitch="30" />
</GameScene>

Простой способ увидеть, как каналы используются и маршрутизируются по вашей сети, — это использовать [умные кабеля](../items-blocks-machines/cables.md), которые отображают на себе пути и использование каналов.

Каналы будут потреблять 1⁄128 ae/t на каждый узел, который они пересекают, это означает, что при
добавлении <ItemLink id="controller" /> для
сети с 8 устройствами и более 96 узлами ваше энергопотребление может фактически
уменьшиться, поскольку изменяется способ распределения каналов.

Следует отметить, что **КАНАЛЫ НЕ ИМЕЮТ НИКАКОГО ОТНОШЕНИЯ К ЦВЕТУ КАБЕЛЕЙ**, цвет кабеля лишь препятствует его подключению.

## Маршрутизация каналов

При использовании <ItemLink id="controller" />,
каналы проходят через 3 этапа. Сначала они проходят по кратчайшему пути через соседние машины к ближайшему [обычному кабелю](../items-blocks-machines/cables.md)
(стеклянный, покрытый или умный). Затем они прокладывают кратчайший маршрут через этот обычный кабель к ближайшему [непрозрачному кабелю](../items-blocks-machines/cables.md)

### !!!ЗАКОНЧИЛ ПРОВЕРЯТЬ ПЕРЕВОД ЗДЕСЬ!!!

(непрозрачный или непрозрачный умный). Затем они выбирают кратчайший маршрут через этот непрозрачный кабель к <ItemLink id="controller" />.
Если кратчайший маршрут уже исчерпан, некоторые [устройства](devices.md) могут не получить необходимые каналы, используйте
цветные кабели, тросовые анкеры и туннели, чтобы обеспечить прохождение каналов по желаемому маршруту.

Например, в данном случае некоторые дисководы не получают каналов, потому что, несмотря на то, что в кабелях достаточно емкости,
каналы пытаются выбрать кратчайший маршрут, перегружая одни кабели и оставляя другие пустыми.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_path_length_issue.snbt" />

  <LineAnnotation color="#33ff33" from="3 .5 1.4" to="0.4 0.5 1.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 .5 1.4" to="0.4 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 0.5 3.6" to="1.4 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.4 0.5 3.6" to="1.4 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#33ff33" from="3 0.5 3.6" to="1.6 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.6 0.5 3.6" to="1.6 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#ff3333" from="3 .5 1.6" to="0.6 .5 1.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#ff3333" from="0.6 .5 1.6" to="0.6 .5 3.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#ff3333" from="0.6 .5 3.4" to="1.4 .5 3.4" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#ff3333" from="3 .5 3.4" to="1.6 .5 3.4" alwaysOnTop={true} thickness="0.05"/>

  <BoxAnnotation color="#dddddd" min="1.2 0.2 3.2" max="1.8 0.8 3.8" alwaysOnTop={true} thickness="0.05">
        Более 8 каналов пытаются пройти через этот участок, поэтому некоторые из них отключаются.
  </BoxAnnotation>

  <IsometricCamera yaw="90" pitch="90" />

</GameScene>

Эту проблему можно решить, более тщательно ограничивая пути, по которым могут проходить каналы. Сети должны иметь древовидную (или кустовидную) структуру.
Следует свести к минимуму петли и неоднозначные пути каналов.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_path_length_issue_fix.snbt" />

  <LineAnnotation color="#33ff33" from="3 .5 1.4" to="0.4 0.5 1.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 .5 1.4" to="0.4 0.5 5.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 0.5 5.6" to="1 0.5 5.6" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#33ff33" from="3 0.5 3.6" to="1.6 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.6 0.5 3.6" to="1.6 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <IsometricCamera yaw="90" pitch="90" />

</GameScene>

## "Неполноценные" сети

Сеть без <ItemLink id="controller" />
считается "неполноценной" и может поддерживать до 8 каналов с помощью устройств.
Как только количество устройств превысит 8, канал сети, используемый устройствами, будет отключен.
Вы можете либо удалить устройства, либо добавить <ItemLink id="controller" />.

В отличие от управляемых сетей, [умные кабели](../items-blocks-machines/cables.md) в "недоразвитых" сетях будут отображать количество
каналов, используемых во всей сети, а не количество каналов, проходящих через этот конкретный кабель.

При использовании "неполноценных" сетей каждое устройство будет
использовать 1 канал по всей сети, что сильно отличается от того, как <ItemLink id="controller" /> распределяет каналы на основе
кратчайшего маршрута.

## Дизайн

Как упоминалось ранее в разделе [маршрутизация каналов](channels.md#маршрутизация-каналов), лучше всего проектировать сеть в виде древовидной структуры, с непрозрачными кабелями, отходящими от <ItemLink id="controller" />, обычными кабелями,
отходящими от , и [устройствами](../ae2-mechanics/devices.md) в друзах по 8 или менее на обычных кабелях.

Вот пример того, чего не следует делать:

Следуя по путям каналов,

1. Сразу же выйдя из мэ-регулятора справа, мы ограничены 8 каналами, потому что дисковод работает как обычный кабель.
Однако, поскольку мы не используем здесь умный кабель, мы не можем увидеть, сколько каналов используется. Осталось 8 каналов.
2. Дисковод занимает один канал.
Осталось 7 каналов.
3. 2 канала подходят к терминалам.
Осталось 5 каналов.
4. Продолжая вправо, интерфейс переходит на другой канал.
Осталось 4 канала.
5. 1 канал идет к поставщику шаблонов.
Осталось 3 канала.
6. Продолжая вправо, 1 канал поднимается до шины импорта.
Осталось 2 канала.
7. Группа поставщиков шаблонов, питающих сборщиков, получает только 2 канала, поэтому 2 из поставщиков не получают каналов.

В конечном итоге ошибка заключается в создании узких мест в каналах и в том, что не продумано, как будут распределяться каналы.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/bad_network_structure.snbt" />

<LineAnnotation color="#33ff33" from="6.5 .5 1.5" to="6 .5 1.5" alwaysOnTop={true} thickness="0.4">
  32 канала
</LineAnnotation>

<LineAnnotation color="#33ff33" from="6 .5 1.5" to="5.5 .5 1.5" alwaysOnTop={true} thickness="0.2">
  8 каналов
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 .5 1.5" to="5.5 1.5 1.5" alwaysOnTop={true} thickness="0.1">
  2 канала
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 .5 1.5" to="5.5 .3 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 1.5 1.5" to="5.5 2.5 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 2.5 1.5" to="5.5 2.5 1.1" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 .5 1.5" to="4.5 .5 1.5" alwaysOnTop={true} thickness="0.158">
  5 каналов
</LineAnnotation>

<LineAnnotation color="#33ff33" from="4.5 .5 1.5" to="4.5 .3 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="4.5 .5 1.5" to="4.5 1.5 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="4.5 .5 1.5" to="3.5 .5 1.5" alwaysOnTop={true} thickness="0.122">
  3 канала
</LineAnnotation>

<LineAnnotation color="#33ff33" from="3.5 .5 1.5" to="3.5 2.5 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="3.5 2.5 1.5" to="3.7 2.5 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="3.5 .5 1.5" to="1.5 .5 1.5" alwaysOnTop={true} thickness="0.1">
  2 канала
</LineAnnotation>

<LineAnnotation color="#33ff33" from="1.5 0.5 1.5" to="1.5 0.3 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="1.5 0.5 1.5" to="0.5 0.5 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="0.5 0.5 1.5" to="0.5 0.5 0.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#ff3333" from="0.5 1.5 1.5" to="0.5 1.3 1.5" alwaysOnTop={true} thickness="0.071">
  Нету каналов
</LineAnnotation>

<LineAnnotation color="#ff3333" from="1.5 1.5 0.5" to="1.5 1.3 0.5" alwaysOnTop={true} thickness="0.071">
  Нету каналов
</LineAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

---

Вот пример хорошей структуры:

<GameScene zoom="2.5" interactive={true}>
  <ImportStructure src="../assets/assemblies/treelike_network_structure.snbt" />

    <BoxAnnotation color="#dddddd" min="6.9 0 4.9" max="9.1 4 7.1" thickness="0.05">
        Обратите внимание, что поставщики шаблонов разделены на отдельные группы по 8.
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="5 4 4" max="8 5 5" thickness="0.05">
        Два обычных кабеля, заполненных каналами, соединяются, поэтому вам понадобится непрозрачный кабель.
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="5 0 13" max="8 1 14" thickness="0.05">
        Различные цвета кабелей используются для предотвращения соединения соседних кабелей.
    </BoxAnnotation>


  <IsometricCamera yaw="315" pitch="30" />
</GameScene>

## Режимы каналов

AE2 10.0.0 для Minecraft 1.18 вводит новые опции, позволяющие изменять поведение каналов AE2 в вашем мире.
В общем разделе (`каналы`) появилась новая настройка, которая управляет этой опцией, а также новая внутриигровая
команда для операторов, позволяющая изменять режим и настройки из игры. Команда `/ae2 channelmode <mode>`
изменяет режим, а `/ae2 channelmode` показывает текущий режим. При изменении режима в игре все существующие сетки
перезагружаются и сразу же начинают использовать новый режим.

Это возрождает и улучшает опцию, которая была доступна в Minecraft 1.12, и вводит лучшие варианты для
игроков, которые просто хотят немного более расслабленного игрового процесса, но не хотят, чтобы механика была полностью удалена.

В следующей таблице перечислены режимы, доступные как в конфигурационном файле, так и в команде.

| Настройка     | Описание                                                                                                                                                                                                                                  |
| ----------    | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `по умолчанию`| Стандартный режим с пропускной способностью каналов кабельных и специальныхсетей, как описано на этом веб-сайте.                                                                                                                          |
| `x2`          | Все каналы имеют 2-х пропускную способность (16 по обычному кабелю, 64 по плотному кабелю, спец. сети поддерживают 16 каналов)                                                                                                            |
| `x3`          | Все каналы имеют 3-х пропускную способность (24 по обычному кабелю, 92 по плотному кабелю, спец. сети поддерживают 24 канала)                                                                                                             |
| `x4`          | Все каналы имеют 4-х пропускную способность (32 на обычному кабелю, 128 по плотному кабелю, спец. сети поддерживают 32 канала)                                                                                                            |
| `бесконечно`  | Все ограничения по каналам сняты. Контроллеры по-прежнему *значительно* снижают энергопотр. сетей. Умн. кабели будут перекл. только между полн. выкл. состоянием (каналы не передаются) и полн. вкл. состоянием (передает 1 или более кан)|