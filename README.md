# replacement-part-cad

Скилл для Claude: воссоздать сломанную пластиковую деталь и напечатать её на FDM-принтере.

**Сначала чертёж, потом 3D.** Claude разбирает фото, видео, скан iPhone и замеры штангенциркулем, рисует 2D-чертёж и согласует его с вами. Только после этого строит параметрическую модель в CadQuery.

Что умеет:
- режимы «по образцу», «новая деталь», «правка параметров», «проверка готового STL»;
- 2D-чертёж (разрез, виды, выносные элементы) с пометками «✓ замерено» и «? допущение»;
- CadQuery-модель: все размеры в `params.json`, допуски посадок отдельно от номиналов; экспорт STEP + STL + 3MF;
- регрессионная проверка размеров и проверка печатаемости: нависания, тонкие и «некратные» стенки, нижние скругления;
- правила геометрии под FDM: ориентация по нагрузке, рёбра, teardrop-отверстия, фаски против «слоновьей ноги», вплавляемые втулки вместо печатной резьбы, защёлки;
- профиль «принтер + пластик» и лесенки-пробники для подбора посадок;
- двухцветная печать через AMS: проект Bambu Studio (.3mf) с уже назначенными филаментами;
- независимый аудит субагентом перед выдачей.

Отработано на Bambu Lab A1 и PETG, но подходит для любого FDM.

## Установка

**Claude Code:**
```
/plugin marketplace add tyhinv/replacement-part-cad
/plugin install replacement-part-cad@replacement-part-cad
```

**Claude.ai / приложение Claude:** скачайте папку `skills/replacement-part-cad`, упакуйте её в zip и загрузите в настройках, в разделе скиллов.

Зависимости ставит сам Claude в песочнице: `cadquery`, `trimesh`, `shapely`, `matplotlib`, `lib3mf` (по необходимости).

## English

A Claude skill for recreating broken plastic parts for FDM printing. The workflow goes from measurements and photos to an agreed 2D drawing, then a parametric CadQuery model (STEP/STL/3MF), printability checks, fit test pieces and a Bambu Studio multi-color project. The skill text is in Russian; Claude follows it fine and answers in your language.

## Откуда идеи

Ссылки и лицензии источников — в конце `SKILL.md`. Текст и код из репозиториев с некоммерческими лицензиями не заимствованы.

## Лицензия

MIT
