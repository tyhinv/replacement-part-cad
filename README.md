# replacement-part-cad

[English below](#english) · Русский

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

A Claude skill for recreating a broken plastic part and printing it on an FDM printer.

**Drawing first, 3D second.** Claude works through your photos, videos, iPhone scans and caliper measurements, draws a 2D drawing and agrees it with you. Only then does it build a parametric CadQuery model.

What it does:
- modes: "from a sample", "new part", "edit parameters", "check an existing STL";
- 2D drawing (section, views, detail views) with "✓ measured" and "? assumption" marks;
- CadQuery model: all dimensions in `params.json`, fit tolerances kept separate from nominal sizes; exports STEP + STL + 3MF;
- regression dimension checks and printability checks: overhangs, thin walls and walls that don't match the line width, fillets on bottom edges;
- FDM design rules: orientation by load, ribs, teardrop holes, chamfers against "elephant's foot", heat-set inserts instead of printed threads, snap-fits;
- a "printer + filament" profile and stepped test pieces for tuning fits;
- two-color printing with AMS: a Bambu Studio project (.3mf) with filaments already assigned;
- an independent review by a subagent before handing over the files.

Developed on a Bambu Lab A1 with PETG, but works for any FDM printer.

The skill text is in Russian. Claude follows it fine and answers in your language.

### Installation

**Claude Code:**
```
/plugin marketplace add tyhinv/replacement-part-cad
/plugin install replacement-part-cad@replacement-part-cad
```

**Claude.ai / Claude app:** download the `skills/replacement-part-cad` folder, zip it and upload it in settings, in the Skills section.

Claude installs the dependencies itself in its sandbox: `cadquery`, `trimesh`, `shapely`, `matplotlib`, `lib3mf` (as needed).

### Credits and license

Sources and their licenses are listed at the end of `SKILL.md`. No text or code was taken from repositories with non-commercial licenses. License: MIT.

## Откуда идеи

Ссылки и лицензии источников — в конце `SKILL.md`. Текст и код из репозиториев с некоммерческими лицензиями не заимствованы.

## Лицензия

MIT
