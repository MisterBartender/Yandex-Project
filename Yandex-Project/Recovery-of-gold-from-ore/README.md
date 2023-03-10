# Предсказание коэффициента восстановления золота из золотосодержащей руды


## Описание проекта
Необходимо подготовить прототип модели машинного обучения для «Цифры». Компания разрабатывает решения для эффективной работы промышленных предприятий.
Модель должна предсказать коэффициент восстановления золота из золотосодержащей руды. В моем распоряжении данные с параметрами добычи и очистки.
Модель поможет оптимизировать производство, чтобы не запускать предприятие с убыточными характеристиками.
Описание данных

## Технологический процесс
- Rougher feed — исходное сырье
- Rougher additions (или reagent additions) — флотационные реагенты: Xanthate, Sulphate, Depressant
- Xanthate **— ксантогенат (промотер, или активатор флотации);
- Sulphate — сульфат (на данном производстве сульфид натрия);
- Depressant — депрессант (силикат натрия).
- Rougher process (англ. «грубый процесс») — флотация
- Rougher tails — отвальные хвосты
- Float banks — флотационная установка
- Cleaner process — очистка
- Rougher Au — черновой концентрат золота
- Final Au — финальный концентрат золота  


## Параметры этапов
air amount — объём воздуха
fluid levels — уровень жидкости
feed size — размер гранул сырья
feed rate — скорость подачи  


## Наименование признаков

Наименование признаков формируется по следующему принципу:  

__[этап].[тип_параметра].[название_параметра]__  

Пример: rougher.input.feed_ag

### Возможные значения для блока [этап]
- rougher — флотация
- primary_cleaner — первичная очистка
- secondary_cleaner — вторичная очистка
- final — финальные характеристики  


### Возможные значения для блока [тип_параметра]
- input — параметры сырья
- output — параметры продукта
- state — параметры, характеризующие текущее состояние этапа
- calculation — расчётные характеристики

### Целевые признаки
- эффективность обогащения чернового концентрата rougher.output.recovery;
- эффективность обогащения финального концентрата final.output.recovery.

## Формула расчёта эффективности 

![](http://latex.codecogs.com/gif.latex?\dpi{110}&space;\bg_white&space;Recovery&space;=&space;\frac{C\times(F&space;-&space;T)}{F\times(C&space;-&space;T)}&space;*&space;100\%)

где:
 - C — доля золота в концентрате после флотации/очистки;
 - F — доля золота в сырье/концентрате до флотации/очистки;
 - T — доля золота в отвальных хвостах после флотации/очистки.
 
 ## Формула итоговой метрики
 ![](http://latex.codecogs.com/gif.latex?%5Cdpi%7B110%7D%20%5Cbg_white%20final-%20sMAPE%20=%2025%5C%25%20%5Ctimes%20sMAPE(rougher)%20&plus;%2075%5C%25%20%5Ctimes%20sMAPE(final)%20)
 
 
## Общий вывод
В процессе работы было сделано следующее:

проведена проверка рассчётов эфективности обогащения;
выявлены и заполнены пропущеные значения;
проведен анализ отсутствующих значений в тестовом наборе;
проверено изменение концентрации металлов на разных этапах очистки;
проведено сравнение распределения размеров гранул сырья;
исследована сумарная концентрация всех веществ на разных стадиях: в сырье, в черновом и финальном концентратах;
написана функция для вычисления итоговой sMAPE;
Обучены различные модели ( LinearRegression, DecisionTreeRegressor, RandomForestRegressor ), выбрана лучшая (RandomForestRegressor) и проверена на тестовой выборке;
Лучшая модель проверена на тестовом наборе данных, и рассчитано sMAPE. Низкое значение sMAPE говорит нам об отличной пригодности выбранной модели. Значение sMAPE лучшей модели и средняя рассчитанная по медианным значениям метрика sMAPE примерно равны.

