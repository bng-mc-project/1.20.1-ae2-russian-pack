---
navigation:
  parent: example-setups/example-setups-index.md
  title: Специализированное локальное хранилище
  icon: drive
---

# Специализированное локальное хранилище

Используя одно из [специальных поведений интерфейса](../items-blocks-machines/interface.md#special-interactions),
[подсеть](../ae2-mechanics/subnetworks.md) может предоставлять содержимое своего хранилища основной сети, не имея возможности
просматривать хранилище основной сети и занимая только 1 [канал](../ae2-mechanics/channels.md).

Это полезно для локального хранения на какой-нибудь ферме, чтобы предметы не переполняли ваше основное хранилище.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/local_storage.snbt" />

<BoxAnnotation color="#dddddd" min="4 0 0" max="5 2 1">
        (1) Некоторый метод импорта предметов (в данном случае интерфейса)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3 0 0" max="4 1 1">
        (2) Диск: содержит несколько ячеек. Ячейки должны быть отфильтрованы в соответствии с результатами работы фермы.
        Ячейки могут иметь карты равного распределения и карты уничтожения переполнения.
        <Row><ItemImage id="item_storage_cell_4k" scale="2" /> <ItemImage id="equal_distribution_card" scale="2" /> <ItemImage id="void_card" scale="2" /></Row>
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3 1 0" max="4 2 0.3">
        (3) Терминал изготовления: он может просматривать содержимое диска в подсети, но не содержимое хранилища вашей основной сети.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 0 0" max="2.3 1 1">
        (4) Интерфейс № 2: в настройке по умолчанию.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1.7 0 0" max="2 1 1">
        (5) Шина хранения: имеет приоритет выше, чем основное хранилище, может фильтроваться в соответствии с выходом фермы.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 2 0.3">
        Терминал изготовления: он может видеть содержимое хранилища основной сети *и* подсети.
  </BoxAnnotation>

<DiamondAnnotation pos="0 0.5 0.5" color="#00ff00">
        В основную сеть
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Настройки

* Первый <ItemLink id="interface" /> (1) просто принимает предметы из любой фермы, которая у вас есть, и отправляет их в подсеть.
* <ItemLink id="drive" /> (2) содержит несколько [ячеек](../items-blocks-machines/storage_cells.md). Ячейки должны быть
  [разбиты на разделы](../items-blocks-machines/cell_workbench.md) в соответствии с результатами работы фермы.
  Ячейки могут иметь <ItemLink id="equal_distribution_card" /> и <ItemLink id="void_card" />.
* Второй <ItemLink id="interface" /> (4) находится в своей настройке по умолчанию.
* У <ItemLink id="storage_bus" /> [приоритет](../ae2-mechanics/import-export-storage.md#приоритет-хранения) установлен
  выше, чем у основного хранилища. Его можно отфильтровать в соответствии с результатом работы фермы.

## Как это работает

* <ItemLink id="interface" /> в подсети показывает <ItemLink id="storage_bus" /> в основной сети, содержание
 <ItemLink id="drive" />. Это означает, что шина хранения может напрямую извлекать предметы из ячеек диска и помещать их в эти ячейки.
* Шина хранения имеет высокий [приоритет](../ae2-mechanics/import-export-storage.md#приоритет-хранения), чтобы предметы предпочтительно
  возвращались в подсеть, а не в основное хранилище.
* Важно отметить, что если ячейки в подсети заполнятся, предметы не будут переполнять основную сеть. Если ферма относится к типу,
 который выходит из строя при переполнии, вместо этого можно использовать <ItemLink id="void_card" /> для удаления лишних предметов. 
* Если ферма производит несколько предметов, <ItemLink id="equal_distribution_card" /> могут предотвратить заполнение всех ячеек одним предметом
и не дать другим предметам быть сохраненными.