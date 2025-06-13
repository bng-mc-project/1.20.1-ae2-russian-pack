---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Каналы
  icon: controller
---

# Каналы

[ME-сети](me-network-connections.md) Applied Energistics 2 требуют каналов для поддержки [устройств](../ae2-mechanics/devices.md), использующих сетевое хранилище или другие сетевые сервисы. Представьте каналы как USB-кабели для всех ваших устройств. У компьютера ограниченное количество USB-портов, и он может поддерживать только определённое количество подключённых устройств. Большинство машин, полноразмерных устройств и стандартных кабелей могут передавать только до 8 каналов. Можно считать полноразмерные устройства и стандартные кабели пучком из 8 "проводов каналов". Однако [плотные кабели](../items-blocks-machines/cables.md#dense-cable) поддерживают до 32 каналов. Единственные другие устройства, способные передавать 32 канала, — это <ItemLink id="me_p2p_tunnel" /> и [Квантовый сетевой мост](../items-blocks-machines/quantum_bridge.md). Каждый раз, когда устройство использует канал, представьте, что вы отключаете один "провод" из пучка, что означает, что этот "провод" больше не доступен дальше по линии.

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
  Все 8 каналов в кабеле использованы, поэтому привод не получает канал.  
  </LineAnnotation>

  <LineAnnotation color="#993333" from="1 .5 .5" to="1.25 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="1.5 .5 .5" to="1.75 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="2 .5 .5" to="2.25 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="2.5 .5 .5" to="2.75 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="3 .5 .5" to="3.25 .5 .5" alwaysOnTop={true}/>

  <DiamondAnnotation pos="3.6 0.5 0.5" color="#ff0000">
        Все 8 каналов в кабеле использованы, поэтому привод не получает канал.
    </DiamondAnnotation>

  <IsometricCamera yaw="15" pitch="30" />
</GameScene>

Простой способ увидеть, как каналы используются и маршрутизируются в вашей сети, — использовать [умные кабели](../items-blocks-machines/cables.md), которые отображают пути и использование каналов.

Каналы потребляют 1⁄128 ae/t за каждый узел, через который они проходят. Это означает, что добавление <ItemLink id="controller" /> для сети с 8 устройствами и более чем 96 узлами может фактически снизить потребление энергии, так как это изменяет распределение каналов.

Важно отметить, что **ЦВЕТ КАБЕЛЯ НЕ ИМЕЕТ НИКАКОГО ОТНОШЕНИЯ К КАНАЛАМ**, он только предотвращает соединение кабелей.

## Маршрутизация каналов

При использовании <ItemLink id="controller" /> каналы маршрутизируются в 3 этапа. Сначала они идут кратчайшим путём через соседние машины к ближайшему [обычному кабелю](../items-blocks-machines/cables.md) (стеклянному, покрытому или умному). Затем они идут кратчайшим путём через этот обычный кабель к ближайшему [плотному кабелю](../items-blocks-machines/cables.md) (плотному или плотному умному). Наконец, они идут кратчайшим путём через этот плотный кабель к <ItemLink id="controller" />. Если кратчайший путь уже перегружен, некоторые [устройства](devices.md) могут не получить свои каналы. Используйте цветные кабели, якоря и туннели, чтобы направить каналы по нужному пути.

Например, в этом случае некоторые приводы не получают каналы, потому что, хотя в кабелях достаточно места, каналы пытаются идти кратчайшим путём, перегружая одни кабели и оставляя другие пустыми.

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
        Более 8 каналов пытаются пройти здесь, поэтому некоторые отключаются.
  </BoxAnnotation>

  <IsometricCamera yaw="90" pitch="90" />

</GameScene>

Эту проблему можно решить, более тщательно ограничив пути, по которым могут идти каналы. Сети должны быть древовидными (или кустообразными). Петли и неоднозначные пути следует минимизировать.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_path_length_issue_fix.snbt" />

  <LineAnnotation color="#33ff33" from="3 .5 1.4" to="0.4 0.5 1.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 .5 1.4" to="0.4 0.5 5.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 0.5 5.6" to="1 0.5 5.6" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#33ff33" from="3 0.5 3.6" to="1.6 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.6 0.5 3.6" to="1.6 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <IsometricCamera yaw="90" pitch="90" />

</GameScene>

## Ad-Hoc сети

Сеть без <ItemLink id="controller" /> считается Ad-Hoc и может поддерживать до 8 устройств, использующих каналы. Если устройств больше, сеть отключит часть из них. Вы можете либо удалить лишние устройства, либо добавить <ItemLink id="controller" />.

В отличие от сетей с контроллером, [умные кабели](../items-blocks-machines/cables.md) в Ad-Hoc сетях показывают общее количество используемых каналов в сети, а не количество каналов в конкретном кабеле.

В Ad-Hoc сетях каждое устройство использует 1 канал на всю сеть, что сильно отличается от распределения каналов в сетях с контроллером.

## Дизайн сети

Как упоминалось в разделе [маршрутизация каналов](channels.md#channel-routing), лучше проектировать сеть в древовидной структуре: плотные кабели ответвляются от контроллера, обычные кабели — от плотных, а [устройства](../ae2-mechanics/devices.md) группируются в кластеры по 8 или меньше на обычных кабелях.

Пример плохого дизайна:

1. Сразу после выхода из контроллера каналы ограничены 8 из-за привода, который действует как обычный кабель. Поскольку здесь не используется умный кабель, нельзя увидеть, сколько каналов занято. Осталось 8 каналов.
2. Привод занимает 1 канал. Осталось 7.
3. 2 канала идут к терминалам. Осталось 5.
4. Интерфейс занимает ещё 1 канал. Осталось 4.
5. 1 канал идёт к поставщику шаблонов. Осталось 3.
6. Импортный шин занимает ещё 1 канал. Осталось 2.
7. Кластер поставщиков шаблонов получает только 2 канала, поэтому 2 из них остаются без каналов.

Ошибка заключается в узком месте и непродуманном распределении каналов.

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
  нет каналов
</LineAnnotation>

<LineAnnotation color="#ff3333" from="1.5 1.5 0.5" to="1.5 1.3 0.5" alwaysOnTop={true} thickness="0.071">
  нет каналов
</LineAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

---

Пример хорошего дизайна:

<GameScene zoom="2.5" interactive={true}>
  <ImportStructure src="../assets/assemblies/treelike_network_structure.snbt" />

    <BoxAnnotation color="#dddddd" min="6.9 0 4.9" max="9.1 4 7.1" thickness="0.05">
        Обратите внимание, что поставщики шаблонов разделены на группы по 8.
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="5 4 4" max="8 5 5" thickness="0.05">
        Два обычных кабеля с полной загрузкой требуют плотного кабеля.
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="5 0 13" max="8 1 14" thickness="0.05">
        Разные цвета кабелей предотвращают их соединение.
    </BoxAnnotation>


  <IsometricCamera yaw="315" pitch="30" />
</GameScene>

## Режимы каналов

AE2 10.0.0 для Minecraft 1.18 вводит новые настройки для изменения поведения каналов. В конфигурации появилась опция (`channels`), а также команда для операторов: `/ae2 channelmode <mode>` для изменения режима и `/ae2 channelmode` для отображения текущего режима. При изменении режима все существующие сети перезагружаются и применяют новый режим.

Это возрождает и улучшает опцию, доступную в Minecraft 1.12, и добавляет новые варианты для игроков, которые хотят более расслабленного геймплея, но не хотят полностью отключать механику.

Доступные режимы:

| Настройка    | Описание                                                                                                                                                                                                                               |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `default`  | Стандартный режим с ограничениями каналов, описанными на этом сайте.                                                                                                                           |
| `x2`       | Все ограничения каналов удваиваются (16 на обычном кабеле, 64 на плотном, Ad-Hoc сети поддерживают 16 каналов).                                                                                                                           |
| `x3`       | Все ограничения каналов утраиваются (24 на обычном кабеле, 92 на плотном, Ad-Hoc сети поддерживают 24 канала).                                                                                                                           |
| `x4`       | Все ограничения каналов учетверяются (32 на обычном кабеле, 128 на плотном, Ad-Hoc сети поддерживают 32 канала).                                                                                                                       |
| `infinite` | Все ограничения каналов снимаются. Контроллеры всё ещё значительно снижают потребление энергии. Умные кабели показывают только наличие каналов (вкл/выкл). |