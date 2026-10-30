# ETL Data Quality Detection

## English

An ML experiment exploring how changes in daily analytical metrics can help detect data quality issues in ETL pipelines.

Using the **Online Retail II** dataset, the notebook builds a daily analytical table with six metrics, generates synthetic data quality issues, and trains five binary classifiers on 20 current and historical features.

Three error types are simulated for training:
- Missing transaction rows.
- Duplicated transaction rows.
- Incorrect sales totals.

**Models:** Logistic Regression, k-NN, SVM (RBF), Random Forest, and Gradient Boosting.

**Evaluation:** A chronological train/validation/test split (60/20/20) is applied to 602 days. Each day has an original and a modified version, producing 1,204 observations. Models are selected using validation F1 and evaluated on a held-out test set.

Random Forest is selected on validation data (**F1 = 0.722**) and achieves **F1 = 0.739** on the test set. SVM achieves the highest test F1 among the five models (**0.773**), but it was not the model selected on validation data.

The notebook also evaluates the trained models on three unseen error mechanisms: missing orders, stale daily metrics, and incorrect price scale. The results show that performance does not necessarily transfer to new error types.

## Русский

ML-эксперимент по обнаружению нарушений качества данных в ETL-процессах на основе изменений ежедневных показателей аналитической витрины.

На датасете **Online Retail II** формируется ежедневная витрина из шести показателей, моделируются искусственные нарушения качества данных и обучаются пять бинарных классификаторов на 20 текущих и исторических признаках.

Для обучения моделируются три типа ошибок:
- Потеря части транзакционных строк.
- Дублирование транзакционных строк.
- Ошибка расчёта суммы продаж.

**Модели:** Logistic Regression, k-NN, SVM (RBF), Random Forest и Gradient Boosting.

**Оценка:** Используется хронологическое разделение train/validation/test в пропорции 60/20/20. Для 602 дней создаются исходная и изменённая версии, всего 1 204 наблюдения. Основная модель выбирается по F1 на валидационной выборке, затем оценивается на тестовой.

По результатам валидации выбрана Random Forest (**F1 = 0,722**), на тестовой выборке она получила **F1 = 0,739**. Наибольший F1 среди пяти моделей на тестовой выборке показала SVM (**0,773**), но она не была выбрана по валидации.

Дополнительно проверяется перенос уже обученных моделей на три новых механизма: потерю целых заказов, устаревшее состояние витрины и ошибку масштаба цены. Результаты показывают, что качество может заметно снижаться на ранее не встречавшихся ошибках.

## Run / Запуск

Requires Python 3, Jupyter Notebook, and `numpy`, `pandas`, `matplotlib`, `scikit-learn`, and `ipykernel`.

Необходимы Python 3, Jupyter Notebook и библиотеки `numpy`, `pandas`, `matplotlib`, `scikit-learn`, `ipykernel`.

Place `online_retail_II.csv.gz` in the same directory as the notebook, then run:

Поместите `online_retail_II.csv.gz` в одну папку с notebook и выполните:

```bash
python3 -m pip install numpy pandas matplotlib scikit-learn notebook ipykernel
jupyter notebook etl-data-quality-detection.ipynb
```

Run all cells in order. The notebook saves `etl_data_quality_results.csv` with the test-set metrics.

Запустите все ячейки последовательно. Notebook создаёт `etl_data_quality_results.csv` с метриками на тестовой выборке.

**Dataset / Датасет:** Online Retail II, UCI Machine Learning Repository.
