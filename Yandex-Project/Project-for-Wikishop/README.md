# Классификация токсичных комментариев 


## Описание проекта
Интернет-магазин «Викишоп» запускает новый сервис. Теперь пользователи могут редактировать и дополнять описания товаров, как в вики-сообществах. То есть клиенты предлагают свои правки и комментируют изменения других. Магазину нужен инструмент, который будет искать токсичные комментарии и отправлять их на модерацию.
Обучите модель классифицировать комментарии на позитивные и негативные. В вашем распоряжении набор данных с разметкой о токсичности правок.

## Описание данных

- text - содержит текст комментария
- toxic - целевой признак

## Общий вывод:

Данные загрежены, обработаны, проведене токенизация и лемматизация.
Определены тестовая и тренеровачная выборки.
TF-IDF подсчитано.
Обучены модели LogisticRegression, DecisionTreeClassifier, RandomForestClassifier, LGBMClassifier, XGBClassifier, и найдены сответствующие гиперпараметры.
Модель LightGBM показала значение метрики качества F1 не меньше 0.75 по условию и равно 0.7680 соответственно.