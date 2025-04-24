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
  left: 77px;
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
# Фаза 1 • Неделя 3 • Понедельник

## Машинное обучение • Основные алгоритмы


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

* разбезрем основные алгоритмы
* ответим на вопрос "какой признак самый важный?"
* визуализируем построенное алгоритмы

---

<!-- _footer: 📝 [KNN classifier](https://matlab1.com/knn-classifier/) -->

# Метод ближайших соседей 

![center h:350](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e7/KnnClassification.svg/1920px-KnnClassification.svg.png) 



---

# Метод ближайших соседей / KNN

* классификация: 
    * берем $k$ соседей и смотрим, какой класс встречается чаще
* регрессия:
    * берем и вычисляем среднее (можно средневзвешенное) значение для нового объекта

---


# Расстояние

* Что значит ближайшие?

Близкие по метрике Минковского: 

$$\rho(x, y) = \left( \sum^{d}_{i=0} |x_i - y_i|^p \right)^{1/p}$$

• при $p=2$ это евклидово расстояние 
• при $p=1$ Манхэттенская метрика
• при $p=\infty$ - метрика Чебышева (наибольшее из всех расстояний)

---

# Метод ближайших соседей: проблема

![center h:380 w:600](https://miro.medium.com/max/938/1*OhaHs0Lb0_AVLGft2dgktA.png)

Если целевой объект расположен далеко, алгоритм все равно классифицирует объект. Можно использовать радиальный вариант. 

---
<!-- _footer: 📝 [r-Nearest neighbors](https://www.geeksforgeeks.org/r-nearest-neighbors/)
 -->
# Радиальный NN / RadiusNN

![center h:400](https://media.geeksforgeeks.org/wp-content/uploads/20190614212554/download-310.png)

Но такой радиус сложно подобрать. 


--- 
# KNN: гиперпараметры

* число соседей / радиус
* метрика 
* способ вычисления весов объектов

--- 


# Decision Tree
* Классификация: игра состоится? 

![h:500 center](https://www.includehelp.com/ml-ai/Images/decision-trees-1.jpg)

---

# Какой признак самый информативный? 



Тот, при использовании которого для классификации, мы получаем наиболее "чистые" подмножества объектов выборки: 

- Признак `Windy` имеет два значения: `Weak` и `Strong`
    - Для `Windy=Weak`: `Play=Yes` – 3 объекта, `Play=No` –  1 объект 
    - Для `Windy=Strong`: `Play=Yes` – 2 объекта, `Play=No` –  4 объекта

- Признак `Humidity` имеет два значения: `High` и `Normal`:
    - Для `Humidity=Normal`: `Play=Yes` – 2 объекта, `Play=No` –  1 объект
    - Для `Humidity=High`: `Play=Yes` – 3 объекта, `Play=No` –  4 объект

--- 
# Оценки гомогенности для разбиений
</br>


![h: 1500 center](https://i.ibb.co/r2vPZCW/Decision-Tree-Page-1.png)

Как измерить гомогенность выборки в полученных разбиениях?

- Коэффициент Джини / Gini impurity: 
$$G = 1 - \Sigma_i p_i^2$$
- Энтропия разбиения:
$$H=- \Sigma p_i \log_2{p_i}$$
$p_i$ – частота объектов класса $i$ в разбиении

---
# Исходное множество

|Разбиение| Entropy|
|-------|--------------|
|Исходное ![w:120](https://i.ibb.co/cwFYLQp/Decision-Tree-Page-2.png)| $-(0.5 \log_2{0.5} + 0.5 \log_2{0.5)}=1$|
|`Windy=Weak` ![](https://i.ibb.co/8BMxTwh/Decision-Tree-Page-3.png)|$-(0.25\log_2{0.25} + 0.75\log_2{0.75)}=0.81$
|`Windy=Strong` ![](https://i.ibb.co/QH60SL7/Decision-Tree-Page-4.png)|$-(0.33\log_2{0.33} + 0.66\log_2{0.66)=0.92}$|

---
# Information gain
$$IG = S_0 - \sum_{i=1}^{q}\dfrac{N_i}{N}S_i,$$ 
- $q$ – число листьев (обычно 2), 
- $N_i$ – число объектов, попавших в $i$-ое разбиение, 
- $N$ – общее число в родительской веришне объектов, 
- $S_0$ – _impurity metric_ (_gini_ или _entropy_) для исходного разбиения, 
- $S_i$ – _impurity metric_ для $i$-го разбиения.

Для разбиения, построоенного по признаку `Windy`: 
$$IG = 1 - 0.4 \times 0.81 - 0.6 \times 0.92 = 0.12$$

---
<!-- _footer: ©️[Feature Importances](https://www.scikit-yb.org/en/latest/api/model_selection/importances.html) -->
# Важность признаков • Feature importances

Суммарный (а в `sklearn` и нормированный) показатель уменьшения гетерогенности выборки используется для оценки важности признаков: если признак выбирался часто и сильно уменьшал энтропию или коэффициент Джини, то он является **информативным**. 

![center h:350](https://www.scikit-yb.org/en/latest/_images/importances-1.png)

---
# Параметры решающих деревьев
- Критерий ветвления: `criterion: gini, entropy`
- Максимальная глубина: `max_depth`
- Минимальное число объектов в листе: `min_samples_leaf`
- Минимальное значение уменьшения гетерогенности для осуществления деления: `min_impurity_decrease`

`sklearn.tree`: [https://scikit-learn.org/stable/modules/tree.html](https://scikit-learn.org/stable/modules/tree.html)

---
# Итоги


* деревья - мощный алгоритм
* но склонен к переобучению
* может выступать в качестве составного блока для более сложных концепций - об этом завтра
* у обученного дерева есть атрибут: `model.feature_importances_`
* может использоваться для задач регрессии: 
  * 📝[CART](https://ru.wikipedia.org/wiki/CART_(%D0%B0%D0%BB%D0%B3%D0%BE%D1%80%D0%B8%D1%82%D0%BC)): classification and regression trees
  * ‼️📝[A Step By Step Regression Tree Example](https://sefiks.com/2018/08/28/a-step-by-step-regression-decision-tree-example/)


