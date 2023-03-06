# Промышленность


## Описание технологического процесса
Сталь обрабатывают в металлическом ковше вместимостью около 100 тонн. Чтобы ковш выдерживал высокие температуры, изнутри его облицовывают огнеупорным кирпичом. Расплавленную сталь заливают в ковш и подогревают до нужной температуры графитовыми электродами. Они установлены в крышке ковша.

Из сплава выводится сера (десульфурация), добавлением примесей корректируется химический состав и отбираются пробы. Сталь легируют — изменяют её состав — подавая куски сплава из бункера для сыпучих материалов или проволоку через специальный трайб-аппарат (англ. tribe, «масса»).

Перед тем как первый раз ввести легирующие добавки, измеряют температуру стали и производят её химический анализ. Потом температуру на несколько минут повышают, добавляют легирующие материалы и продувают сплав инертным газом. Затем его перемешивают и снова проводят измерения. Такой цикл повторяется до достижения целевого химического состава и оптимальной температуры плавки.

Тогда расплавленная сталь отправляется на доводку металла или поступает в машину непрерывной разливки. Оттуда готовый продукт выходит в виде заготовок-слябов (англ. slab, «плита»).

## Процесс обработки

- сталь заливают в ковш
- подогрев до нужной температуры
- вывод серы, добавление примеси и отбор пробы
- измерение температуры
- проводение химического анализа
- повышение температуры
- добавление легирующих материалов
- продувка сплава инертным газом
- перемешивание
- достижение целевого химического состава и оптимальной температуры плавки

## Описание данных

- data_arc.csv — данные об электродах
- data_bulk.csv — данные о подаче сыпучих материалов (объём)
- data_bulk_time.csv — данные о подаче сыпучих материалов (время)
- data_gas.csv — данные о продувке сплава газом
- data_temp.csv — результаты измерения температуры
- data_wire.csv — данные о проволочных материалах (объём)
- data_wire_time.csv — данные о проволочных материалах (время)
- Во всех файлах столбец key содержит номер партии. В файлах может быть несколько строк с одинаковым значением key: они - соответствуют разным итерациям обработки.

## Общий вывод:

Целью исследования являлась оптимизация производственных расходов. Поставленная задача - определение финального значения температуры сплава в плавильном ковше. В качестве входных данных имелись объемные таблицы с информацией о времени, количестве добавок, температуре и прочее.

В процессе предобработки было выявлено следующее - данные являются достаточно "сырыми", т.е. имеют большое количество пропусков, несостыковок по времени. Так же, имелись партии металла, которые в процессе производства не прошли необходимое количество стадий. Возможно, имел место технический сбой. Несмотря на вышеперечисленное удалось выделить выборку в ~ 2100 объектов.

Обучили 5 моделей. От простой линейной регрессии до бустингов. Самой результативной оказалась RandomForest.

Можно продолжить улучшать модель, как пример - алгоритм автоматической генерации признаков, на основе имеющихся. Возможно в данных еще осталась большая доля информации, которая поможет сильно уменьшить ошибку предсказания. Так же можно подобрать лучшие параметры и для бустинга, однако, каждый из способов - это прежде всего время, которое в определенных моментах ограничено.