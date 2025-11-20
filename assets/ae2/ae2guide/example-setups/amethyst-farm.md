---
navigation:
  parent: example-setups/example-setups-index.md
  title: Ферма аметистов
  icon: minecraft:amethyst_shard
---

# Ферма аметистов

В то время как <ItemLink id="growth_accelerator" /> работает с аметистом, обычные методы фильтрации [бутонов истинного кварца](../items-blocks-machines/budding_certus.md) с помощью <ItemLink id="annihilation_plane" /> не работают с бутонами аметистами. В отличие от незрелых бутонов истинного кварца из которых выпадают <ItemLink id="certus_quartz_dust" />, из незрелых аметистовых бутонов ничего не выпадает, поэтому плоскость уничтожения всегда будет их ломать, поскольку сеть всегда может хранить "ничего".

Обходной путь заключается в том, чтобы зачаровать плоскость уничтожения шелковым касанием. Тогда незрелые аметистовые бутоны *действительно* роняют что-то
(различные стадии физических аметистовых бутонов) и, таким образом, могут быть отфильтрованы.

Затем <ItemLink id="minecraft:amethyst_cluster" /> необходимо снова разместить с помощью <ItemLink id="formation_plane" />, чтобы затем
снова разбить с помощью <ItemLink id="annihilation_plane" /> без шелкового касания, чтобы получить <ItemLink id="minecraft:amethyst_shard" />.

Обратите внимание, что из-за направленности кластера непосредственно напротив плоскости формирования должен находиться сплошной блок.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/amethyst_farm.snbt" />

  <BoxAnnotation color="#dddddd" min="2.7 1 1" max="3 2 2">
        (1) МЭ плоскость уничтожения № 1: нет графического интерфейса для настройки, но зачарован Шелковым касанием.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2 1 1" max="2.3 2 2">
        (2) МЭ плоскость формирования: отфильтровано на аметистовую друзу.
        <ItemImage id="minecraft:amethyst_cluster" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1.3 0.7 1" max="2 1 2">
        (3) МЭ плоскость уничтожения № 2: нет графического интерфейса для настройки, но может быть зачарована с помощью Удачи.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 0 1" max="1.3 1 2">
        (4) Шина хранения № 1: фильтруется на аметистовый осколок
        <ItemImage id="minecraft:amethyst_shard" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 0 .7" max="1 1 1">
        (5) Шина хранения № 2: фильтруется на аметистовый осколок. Имеет приоритет выше, чем ваше основное хранилище.
        <ItemImage id="minecraft:amethyst_shard" scale="2" />
  </BoxAnnotation>

<DiamondAnnotation pos="0 0.5 0.5" color="#00ff00">
        В основную сеть
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Настройки

* Первая <ItemLink id="annihilation_plane" /> (1) не имеет графического интерфейса и не может быть настроена, но должна быть зачарована на шёлковое касание.
* <ItemLink id="formation_plane" /> (2) отфильтровывается на <ItemLink id="minecraft:amethyst_cluster" />.
* Вторая <ItemLink id="annihilation_plane" /> (3) не имеет графического интерфейса и не может быть настроена, но может быть зачарована на удачу.
* Первая <ItemLink id="storage_bus" /> (4) фильтруется на <ItemLink id="minecraft:amethyst_shard" />.
* Вторая <ItemLink id="storage_bus" /> (5) фильтруется на <ItemLink id="minecraft:amethyst_shard" />, и его
  [приоритет](../ae2-mechanics/import-export-storage.md#приоритет-хранения) установлен выше, чем у вашего основного хранилища.

## Как это работает

1. Первая <ItemLink id="annihilation_plane" /> пытается разрушить то, что находится перед ним, но может разрушить только <ItemLink id="minecraft:amethyst_cluster" />,
поскольку единственным хранилищем в подсети является <ItemLink id="formation_plane" />, отфильтрованный на аметистовую друзу. Это работает только потому, что
плоскость зачарована шелковым касанием, иначе она могла бы сломать незрелые бутоны, потому что они ничего не роняют.
2. <ItemLink id="formation_plane" /> ставит друзу на блок, противоположный ему.
3. Вторая <ItemLink id="annihilation_plane" /> разбивает друзу, производя <ItemLink id="minecraft:amethyst_shard" />.
4. Первая <ItemLink id="storage_bus" /> хранит осколки в бочке. Технически это не требует фильтрации, поскольку единственное,
с чем должна сталкиваться вторая плоскость уничтожения, — это полностью сформировавшиеся друзу.
5. Вторая <ItemLink id="storage_bus" /> предоставляет основной сети доступ ко всем осколкам аметиста в бочке. Он установлен на
высокий [приоритет](../ae2-mechanics/import-export-storage.md#приоритет-хранения), чтобы осколки аметиста предпочтительно
возвращались в бочку, а не в ваше основное хранилище.
