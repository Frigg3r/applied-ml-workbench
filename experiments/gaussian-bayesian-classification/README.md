# Gaussian Bayesian Classification

## English

A custom Gaussian Bayesian classifier implemented and visualized on the **Iris** dataset using petal length and petal width.

The notebook includes Gaussian class-density contours, decision boundaries, and highlighted classification errors on the training and test sets. The model estimates class-specific means, prior probabilities, and **full covariance matrices** (QDA-style classification).

**Results:** 98.10% training accuracy (103/105) and 93.33% test accuracy (42/45) on a stratified 70/30 split (`random_state=42`). These results reflect a single, small test split and do not guarantee generalization performance.

## ___________________________________________________________________

Собственная реализация байесовского классификатора с гауссовскими распределениями на датасете **Iris («Ирисы»)** с использованием двух признаков: длины и ширины лепестка.

В ноутбуке представлены линии уровня плотности распределений классов, границы принятия решений и ошибки классификации на обучающей и тестовой выборках. Модель оценивает средние векторы, априорные вероятности классов и **полные ковариационные матрицы** (подход, близкий к QDA).

**Результаты:** точность на обучающей выборке - 98,10% (103/105), на тестовой- 93,33% (42/45). Использовано стратифицированное разбиение 70/30 (`random_state=42`). Эти значения получены на одном небольшом разбиении и не гарантируют аналогичную точность на других данных.

## Run / Запуск

Requires Python 3 and `numpy`, `scipy`, `scikit-learn`, `matplotlib`, and `notebook`.

Для запуска необходимы Python 3 и библиотеки `numpy`, `scipy`, `scikit-learn`, `matplotlib`, `notebook`.

```bash
python -m pip install numpy scipy scikit-learn matplotlib notebook
jupyter notebook gaussian-bayesian-classification.ipynb
```
