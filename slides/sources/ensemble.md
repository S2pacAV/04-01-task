---
marp: true
# Define title slide
_class: invert
_backgroundColor: #4520ab;
_paginate: skip;
_footer: 
# _header: "![](https://elbrusboot.camp/static/newLogo-00ed4b8011624cd94aa1812d35f25088.svg)"
---


<style>
img[alt~="center"] {
  display: block;
  margin: 0 auto;
}
h1 {
  position: absolute;
  left: 50px;
  top: 15px;
  right: 80px;
  height: 70px;
  line-height: 70px;
  margin-bottom: 20px;
  color: #4520ab;
  font-size: 28pt

}
a {
  color: #4520ab;
}
</style>

# Фаза 1 • Неделя 3 • Вторник


## Ансамблирование моделей • Ensembling

---
<!--- backgroundColor: white --->
<!--- paginate: true --->
<!--- header: "![](aux/Elbrus-bootcamp-RU.png)" --->

<style>
header {
    height: 675px;
    right: 20px;
    /* margin-bottom: 80px; */
}
header img {
    height: 60px;
    float: right;
 }
</style>




# Сегодня

* ответим на вопрос "как можно соедининть несколько моделей?"
* разберем наиболее популярные варианты
* установим и запустим самые мощные библиотеки для работы с ансамблями моделей

---
<!-- _footer: 📝 [Hands-On Machine Learning with Scikit-Learn and TensorFlow: Concepts, Tools, and Techniques to Build Intelligent Systems](https://www.amazon.com/dp/1491962291) -->

# Голосование / Voting

![center h:300](https://miro.medium.com/max/1400/1*I7NsQXwyR36XK62s1iDNzQ.png)

* __Hard voting__: классификаторы предсказывают классы - выбираем наиболее частотный
* __Soft voting__: классификаторы предсказывают вероятности - усредняем вероятности по классам 

---
<!-- _footer: 📝 [Hands-On Machine Learning with Scikit-Learn and TensorFlow: Concepts, Tools, and Techniques to Build Intelligent Systems](https://www.amazon.com/dp/1491962291) -->

# Голосование / Voting

![center h:500](https://miro.medium.com/max/1400/1*I7NsQXwyR36XK62s1iDNzQ.png)

> Что делать с задачей регрессии? 


---

# Бутстреп / Bootstrap

![center](https://miro.medium.com/max/1400/1*iH5w0MBdiOlxDOCX6nmqqw.png)

---

# Бэггинг / Bagging

1. Основная идея: формируем _boostrap_ выборки
    - Обучаем одну простую модель на каждой выборке
2. Агрегируем предсказания всех моделей


---
<!-- _footer: 🐍[`sklearn.ensemble`: scikit-learn.org](https://scikit-learn.org/stable/modules/ensemble.html#forests-of-randomized-trees) -->
# Случайный лес / Random Forest 


1. Формируем _N_ boostrap-выборок из исходного датасета
2. Обучаем __одно__ дерево на каждой из _N_ выборок
3. Для предсказания агрегируем результаты каждого дерева: наиболее частотный класс в случае классификации, усредненное значение в случае регрессии: 
  * Классификация - самый частотный класс
  * Регрессия - усредняем предсказания


Параметры
- число деревьев: `n_estimators`
- \+ все те же, что для деревьев



--- 
# Стекинг / Stacking 

1. Разделить обучающую выборку на 2 части: `train_1` и `train_2`
2. Выбрать _L_ базовых моделей, одну мета-модель
3. Обучить _L_ базовых моделей на `train_1` 
4. Сделать _L_ прогнозов для объектов `train_2` 
5. Обучить мета-модель на результатах предсказаний базовых моделей

---
# Стекинг / Stacking

![h:500 center](https://i.ibb.co/tJD25sQ/stacking.png) 

---
# Стекинг / Stacking

- Нужно много данных
- Нужно много мощностей 
- Нужно много времени

- Зато оригинально

`sklearn`: [scikit-learn.org](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.StackingRegressor.html)

📝[Про настройку гиперпараметров ансамблей моделей машинного обучения](https://habr.com/ru/post/672486/)

---
# Бустинг / Boosting

- Строим алгоритмы последовательно
- Каждый следующий исправляет суммарную ошибку предыдущих
- Решение принимаем взвешенным голосованием

---
# Адаптивный бустинг / AdaBoost

Бустинг на решающих деревьях

![center h:400](https://lambda-it.ru/media/editor/bos_20190327103839388149.jpg)

---
# Адаптивный бустинг / AdaBoost

Бустинг на линейных моделях

![center h:400](https://ars.els-cdn.com/content/image/3-s2.0-B9780128177365000090-f09-18-9780128177365.jpg)


---
# Градиентный бустинг / Gradient Boosting

- $x^i$ – множество объектов обучающей выборки объемом $l$
- $y^i$ – истинные ответы обучающей выборки
- $a_i(x)$ - $i$-ый алгоритм  
- $Q(y, a(x)) = \dfrac{1}{l}\sum_{i=1}^{l}\mathcal{L}(y^i, a(x^i))$ – функция потерь


---
![h:700 center](https://amueller.github.io/ml-training-intro/slides/images/grad_boost_regression_steps.png)

---
# Градиентный бустинг / Gradient Boosting

- Например, построены $k$ алгоритмов, нужно построить $a_{k+1}$ алгоритм c $c_{k+1}$ весом
- Функция потерь для одного $i$-го объекта: 
$$
\mathcal{L(y^i, a(x^i)) = \mathcal{L}(y^i, c_1 a_1(x^i) + \dots + c_{k}a_{k}(x^i) + {c_{k+1}a_{k+1}(x^i)}})
$$

---
<!-- _footer: 📝 [Gradient boosting: Distance to target](https://explained.ai/gradient-boosting/L2-loss.html) -->

# Градиентный бустинг / Gradient Boosting

![center h:400](https://explained.ai/gradient-boosting/images/golf-dir-vector.png)


---
# Градиентный бустинг / Gradient Boosting

- Базовые модели могут быть любыми, но лучше деревьями
- Решает задачи классификации, регрессии, ранжирования (не очень быстро)
- Нужна большая выборка
- Реализации: 


  - `sklearn.ensemble`: [scikit-learn.org](https://scikit-learn.org/stable/auto_examples/ensemble/plot_gradient_boosting_regression.html) 
  - Extreme Gradient Boosting / `xgboost`: [xgboost.readthedocs.io](https://xgboost.readthedocs.io/) 
  - Light Gradient Boosting Machine / `lighgbm`: [lightgbm.readthedocs.io](https://lightgbm.readthedocs.io/en/latest/)
  - Categorical Boosting / `catboost`: [catboost.ai](https://catboost.ai/)
  - Про сравнения и детали реализаций можно почитать тут: 
    * [CatBoost vs. Light GBM vs. XGBoost](https://towardsdatascience.com/catboost-vs-light-gbm-vs-xgboost-5f93620723db)
    * [When to Choose CatBoost Over XGBoost or LightGBM [Practical Guide]](https://neptune.ai/blog/when-to-choose-catboost-over-xgboost-or-lightgbm)


---

# Итоги

- **Voting**: берем произвольные модели, а результаты агрегируем произвольным образом
- **Бэггинг**: строим бустреп подвыборки и обучаем простые модели на каждой из выборок 
  - пример: случайный лес
- **Стекинг**: используем предсказания моделей в качестве признаков для обучения мета-модели
- **Бустинг**: последовательно строим модели, каждая следующая исправляет ошибку предыдущих
  - Бустинг пока еще [лучшее](https://arxiv.org/pdf/2110.01889.pdf) решение для табличных данных