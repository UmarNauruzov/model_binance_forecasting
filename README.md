# Cкрипт для сбора и обработки данных с использованием API Binance и прогнозирования временных рядов с помощью LSTM-модели.

#### Содержание
1. Вступление
2. Клонируйте репозиторий
3. Установка
    - [Linux](#3-Установка)
    - [Windows 10/11](#3-Установка) 
4. Решение

## 1. Вступление

# Задача:
#### Разработать скрипт для сбора и обработки данных с использованием API Binance и прогнозирования временных рядов с помощью LSTM-модели.

Этапы выполнения задания:

1. Изучить документацию RESTful API Binance (https://binance-docs.github.io/apidocs/spot/en/) и написать скрипт на Python с использованием библиотеки Requests, чтобы получить данные о котировках криптовалют. Сохранить полученные данные в формате CSV.

2. Загрузить полученный CSV-файл с данными в Python с использованием библиотеки Pandas и выполнить предварительную обработку данных (например, удаление пропусков, преобразование даты и времени, масштабирование).

3. С использованием библиотеки NumPy, разделить данные на обучающую и тестовую выборки.

4. Создать и обучить LSTM-модель с использованием библиотеки Keras или TensorFlow на основе подготовленных данных. Подобрать архитектуру и гиперпараметры модели, чтобы достичь наилучшего качества прогнозирования.

5. Оценить качество модели на тестовой выборке, используя подходящие метрики, такие как среднеквадратичная ошибка (MSE) или средняя абсолютная ошибка (MAE).

6. Визуализировать предсказания модели для тестовой выборки на графике с помощью библиотеки Matplotlib или Plotly. Вывести график с предсказанием на час вперед от последних полученных данных.



## 2. Клонируйте репозиторий

Перейдите в пустую папку по вашему выбору.

```git clone https://github.com/UmarNauruzov/model_binance_forecasting.git```


## 3. Установка
<details open>
<summary>For Linux</summary>

```shell
python3 -m venv .env
source .env/bin/activate

pip install requests
pip install csv
pip install datetime 
pip install numpy
pip install pandas 
pip install matplotlib.pyplot
pip install seaborn as sns
pip install sklearn.preprocessing 
pip install keras
pip install sklearn.feature_selection
pip install keras.models import Sequential
pip install keras.layers import Dense, LSTM
pip install tqdm import trange
```
</details>

<details>
<summary> For Windows 10/11</summary>

```shell
python -m venv .env
.env\Scripts\activate

pip install requests
pip install csv
pip install datetime 
pip install numpy
pip install pandas 
pip install matplotlib.pyplot
pip install seaborn as sns
pip install sklearn.preprocessing 
pip install keras
pip install sklearn.feature_selection
pip install keras.models import Sequential
pip install keras.layers import Dense, LSTM
pip install tqdm import trange
```
</details>

## 4. Решение

В начале мною был реализован скрипт на языке программирования python c использованием API Binance, чтобы получить и сохранить исторические данные торгов для заданной валютной пары и интервала времени.

Далее мною были выделены главные признаки.

#### Нецелевые признаки:
* Open time(время открытия)
* High(максимум)
* Low(минимум)

#### Целевой признак:
* Close(цена закрытия)

После чего данные были нормализованы и разделены на обучающие(80%) и тестовые(20%) и поданы на вход нейросети.

### Схема нейросети №1(LSTM-модели):

![схема модели](https://github.com/UmarNauruzov/model_binance_forecasting/blob/main/model.png)

#### Визуальное представление предсказания модели для тестовой выборки:

![предсказания](https://github.com/UmarNauruzov/model_binance_forecasting/blob/main/model_predict.png)

### Схема нейросети №2(не LSTM-модели):

![схема модели_1](https://github.com/UmarNauruzov/model_binance_forecasting/blob/main/схема_нейросети_1.png)

#### Визуальное представление матрицы ошибок:

![матрица ошибок](https://github.com/UmarNauruzov/model_binance_forecasting/blob/main/матрица_ошибок.png)


### Run in `Google Colab`

 <a href="https://colab.research.google.com/drive/1Zkn6i85-MKLNL-ijVe_QQId1ymvDzSUN?usp=sharing"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a>
