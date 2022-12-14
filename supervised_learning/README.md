## Построение предсказательной системы прогнозирования оттока клиентов в коммерческом банке

 **Цель проекта:**

  Требуется построить модель для задачи *классификации*, которая спрогнозирует возможную потерю клиента банком. Необходима модель с максимально большим значением `F1-меры`. Чтобы заказчик принял работу, нужно довести метрику по крайней мере до 0.59. Дополнительно заказчик хочет измерить AUC-ROC, сравнивая её значение с F1-мерой.

  Данные поступили в удволетворительном качестве. Названия столбцов приведены в соответствие с PEP8. Были обнаружены пропуски значений в признаке tenure, принято решение заменить пропуски на медианное значение по категории возраста клиента.

Отметим, что доля положительных классов в целевом признаке - 20.4%. Присутствует незначительный дисбаланс класса.`

Проверили две модели:
 * Логистическая регрессия (LogisticRegression
 * Случайный лес(RandomForestClassifier)

Применены были 4 стратегии борьбы с несбалансированными классами:
   - Применение параметра `class_weight='balanced'` при построении модели.
   - Увеличение выборки (Upsampling)
   - Уменьшение выборки (Downsampling)
   - Изменения порога классификации (Change threshold)

Более точной моделью стал `RandomForestClassifier` с параметрами: criterion='entropy', max_depth=26, min_samples_leaf=5,
min_samples_split=3, n_estimators=67, random_state=rnd_st, class_weight='balanced', который дал метрику f1 в `0.6298` на валидационной и в `0.67703`3 на тестовой выборке.
