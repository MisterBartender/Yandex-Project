# Прогнозирование оттока клиентов банка


## Описание проекта
Из «Бета-Банка» стали уходить клиенты. Каждый месяц. Немного, но заметно. Банковские маркетологи посчитали: сохранять текущих клиентов дешевле, чем привлекать новых.
Нужно спрогнозировать, уйдёт клиент из банка в ближайшее время или нет. Мне предоставлены исторические данные о поведении клиентов и расторжении договоров с банком.
## Описание данных
- RowNumber — индекс строки в данных
- CustomerId — уникальный идентификатор клиента
- Surname — фамилия
- CreditScore — кредитный рейтинг
- Geography — страна проживания
- Gender — пол
- Age — возраст
- Tenure — количество недвижимости у клиента
- Balance — баланс на счёте
- NumOfProducts — количество продуктов банка, используемых клиентом
- HasCrCard — наличие кредитной карты
- IsActiveMember — активность клиента
- EstimatedSalary — предполагаемая зарплата
- Exited — Целевой признак, факт ухода клиента

## Вывод:

В ходе работы, было сделано следующее:

подготовка данных, преобразование и последующее формирование выборок
обучение модели без учёта дисбаланса в данных
борьба с дисбалансом и последующее обучение модели путём принятия параметра автоматической регулировки весов и с помощью функции Upsampling
визуализация AUC-ROC для каждой из моделей после больбы с дисбалансом
принятие финальной модели на основе алгоритма "RandomForest", для которой достигнуто значение меры F1>=0.59.