# 🧠 Обнаружение болезни Паркинсона с помощью XGBoost

## 📋 Описание проекта

Этот проект направлен на раннюю диагностику болезни Паркинсона с использованием алгоритмов машинного обучения. Модель анализирует акустические параметры голоса для определения наличия заболевания.

### 🎯 Цель
Разработать точную модель для автоматического обнаружения болезни Паркинсона на основе анализа голосовых характеристик пациента.

## 📊 Датасет

### Источник
[Parkinson's Disease Data Set](https://www.kaggle.com/datasets/vikasukani/parkinsons-disease-data-set) из UCI Machine Learning Repository

### Структура данных
- **Количество записей**: 195
- **Признаков**: 23
- **Целевая переменная**: `status` (1 = болезнь есть, 0 = здоров)

### Основные признаки
- **MDVP:Fo(Hz)** - Средняя частота голоса
- **MDVP:Fhi(Hz)** - Максимальная частота голоса
- **MDVP:Flo(Hz)** - Минимальная частота голоса
- **MDVP:Jitter(%)** - Вариации частоты
- **MDVP:Shimmer** - Вариации амплитуды
- **RPDE, D2** - Нелинейные динамические характеристики

## 🚀 Используемые технологии

- **Python 3.x**
- **Pandas** - обработка и анализ данных
- **NumPy** - числовые вычисления
- **Scikit-learn** - машинное обучение и предобработка
- **XGBoost** - градиентный бустинг
- **Matplotlib/Seaborn** - визуализация данных
- **Jupyter Notebook** - интерактивная разработка

## 📈 Методология

### Этапы проекта

1. **Загрузка и исследование данных**
   - Анализ структуры датасета
   - Проверка баланса классов
   - Описательная статистика

2. **Предобработка данных**
   - Нормализация признаков (MinMaxScaler от -1 до 1)
   - Удаление идентификаторов пациентов
   - Разделение на обучающую и тестовую выборки

3. **Визуализация**
   - Распределение классов
   - Матрица корреляций
   - Boxplot признаков
   - ROC-кривая
   - Важность признаков

4. **Моделирование**
   - Базовая модель XGBoost
   - Оптимизация гиперпараметров
   - Кросс-валидация

5. **Оценка качества**
   - Точность (Accuracy)
   - Precision, Recall, F1-score
   - Матрица ошибок
   - AUC-ROC

## ⚙️ Оптимизация модели

### Базовые гиперпараметры
```python
XGBClassifier(
    objective='binary:logistic',
    n_estimators=200,
    max_depth=4,
    learning_rate=0.05,
    subsample=0.8,
    colsample_bytree=0.8,
    reg_alpha=0.1,
    reg_lambda=1.0,
    min_child_weight=1,
    random_state=42
)

Основные зависимости:
pandas>=1.3.0
numpy>=1.21.0
scikit-learn>=1.0.0
xgboost>=1.5.0
matplotlib>=3.4.0
seaborn>=0.11.0
Запуск:
jupyter notebook parkinson_detection.ipynb
