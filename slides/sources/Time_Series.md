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

# Фаза 1 • Неделя 4 • Среда

## Анализ временных рядов • Time Series Analysis

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

* области применения методов анализа временных рядов
* базовые методы
* учет различных компонентов во временных рядах
* библиотеки для анализа временных рядов

---

![center w:1100](https://i.stack.imgur.com/Nnxyz.png)

---

# Сферы применения

* финансовая область
* мониторинг состояния оборудования
* климатические исследования
* естесственно-научные области

Естесственным образом возникают в областях, где измерения носят интервальный характер. 

> Две самые типичные задачи: определение природы временного ряда и прогнозирование значение временного ряда


---  

<!-- _footer: 📝[Moving Averages: Smoothing Out the Noise for Better Predictions](https://www.alpharithms.com/moving-averages-083315/)  -->
#  Скользящее среднее

$$ \hat{y}_{t} = \frac{1}{k} \displaystyle\sum^{k}_{n=1} y_{t-n}$$

В качестве следующего значения используем среднее значение последних $k$ наблюдений. 

![center h:250](https://www.alpharithms.com/wp-content/uploads/1265/5-Day-SMA-Example-Diagram.jpg)



---

# Взвешенное скользящее среднее

$$ \hat{y}_{t} = \displaystyle\sum^{k}_{n=1} \omega_n y_{t-n}$$

В качестве следующего значения используем средне-взвешенное значение последних $k$ наблюдений с ограничением $\sum_{n=1}^{k}w_n=1$

--- 
# Экспоненциальное сглаживание

Взвешиваем __все__ доступные наблюдения с экспоненциально убывающими весами

$$\hat{y}_{t} = \alpha \cdot y_{t-1} + (1-\alpha) \cdot \hat y_{t-1}$$

* $y_t$ - настоящее значение временного ряда на шаге $t$
* $\alpha$ - параметр сглаживания


---
# Двойное экспоненциальное сглаживание

Разбиваем наше значение на два компонента: уровень и тренд

$$
\begin{aligned}
& \ell_t = \alpha y_t + (1-\alpha)(\ell_{t-1} + b_{t-1})\\ 
& b_t = \beta(\ell_t - \ell_{t-1}) + (1-\beta)b_{t-1}\\ 
& \hat{y}_{t+1} = \ell_t + b_t
\end{aligned}
$$

$b$ – тренд 
$\ell$ – уровень
$\hat{y}$ –  итоговое значение предсказания вычисляется как сумма тренда и уровня 

$\alpha$ – параметр сглаживания ряда вокруг тренда
$\beta$ – сглаживание тренда

--- 
# Тройное экспоненциальное сглаживание
__Модель Хольта-Винтерса__
</br>

$$
\begin{aligned}
&\ell_t = \alpha(y_t - s_{t-L}) + (1-\alpha)(\ell_{t-1} + b_{t-1})\\ 
&b_t = \beta(\ell_t - \ell_{t-1}) + (1-\beta)b_{t-1}\\ 
&s_t = \gamma(y_t - \ell_t) + (1-\gamma)s_{t-L}\\ 
&\hat{y}_{t+m} = l_t + mb_t + s_{t-L+1+(m-1)modL}
\end{aligned}
$$
$s$ – сезонность, $m$ - число периодов, на которые хотим сделать прогноз, $L$ - индекс сезонности

<br>

🐍[`statsmodels`](https://www.statsmodels.org/dev/generated/statsmodels.tsa.holtwinters.ExponentialSmoothing.html)

---

# Стационарность временного ряда

Для станционарного временного ряда характерно: 
- отсутствие изменений матожидания во времени
- отсутствие изменений дисперсии во времени
- отсутствие изменения ковариацонной функции во времени

---

# Стационарность временного ряда 

![center h:180](https://hsto.org/files/20c/9d8/a63/20c9d8a633ec436f91dccd4aedcc6940.png)

![center h:180](https://hsto.org/files/b88/eec/a67/b88eeca676d642449cab135273fd5a95.png)

![center h:180](https://hsto.org/files/2f6/1ee/cb2/2f61eecb20714352840748b826e38680.png)

---

# Стационарность временного ряда

Нестационарный временной ряд неудобен для исследования: 

- большинство моделей строят прогноз по статистическим данным, если они нестабильны, то и прогноз будет нестабильным
- бороться с нестационарностью можно
- для проверки на стационарность используется тест Дики-Фуллера [[1](https://ru.wikipedia.org/wiki/Тест_Дики_—_Фуллера)] [[2](https://www.statsmodels.org/stable/generated/statsmodels.tsa.stattools.adfuller.html)]
  - Нулевая гипотеза: _временной ряд не является стационарным_

--- 
<!-- _footer: ©️[How to find the Q and P values in autocorrelation and partial autocorrelation plots?](https://i.stack.imgur.com/yF5K2.png) -->
# Автокорреляция / AutoCorrelationFunction / ACF

> Корреляция ряда величин с самим собой: для временного ряда с самим собой со сдвигом по времени

![center h:330](https://i.stack.imgur.com/yF5K2.png)

Автокорреляционная функция показывает зависимость показателя корреляции от величины сдвига

---

<!-- _footer: 📝[Understanding partial autocorrelation](https://www.machinelearningmastery.ru/understanding-partial-auto-correlation-fa39271146ac/) 🎥[Пример подсчёта частной автокорреляционной функции AR(1) процесса](https://www.youtube.com/watch?v=-2k-DTnslzw)   -->
# Частичная автокорреляция / Partial ACF / PACF

Показывает корреляцию ряда с самим собой с вычетом промежуточных влияний
<br>
![center h:400](https://www.machinelearningmastery.ru/img/0-783196-281639.png)


--- 
# Модель $(S)ARIMA (p, d, q)(P, D, Q)_s$

* $p$ – порядок авторегрессионной модели (AR), выбирается по PACF
  - номер последнего ненулевого элемента на графике PACF
* $d$ – порядок интегрирования ряда 
  - с каким лагом дифференцировали
* $q$ – порядок модели MA (moving average), выбирается по ACF
  - номер последнего ненулевого элемента на графике ACF

---
# Модель $(S)ARIMA (p, d, q)(P, D, Q)_s$

* $P$ – порядок сезонной составляющей
  -  смотрим на лаги, кратные размеру сезонности, например: 12, 24, 36... (PACF)
* $D$ – порядок интегрирования сезонной составляющей
* $Q$ – порядок сезонной составляющей
  - смотрим на лаги, кратные размеру сезонности, но на ACF
* $s$ – размерность сезонности (месяц и т.д.)

---

# Итоги

* два самых распространненых подхода: 
  - эконометрический (скользящее среднее, сезонности, тренды и тд)
    * о нем чаще спрашивают на собеседованиях
  - ML-подход: рассматриваем как задачу регрессии (при этом как приготовить признаки из одного временного ряда - отдельный вопрос)
    - В частности можно использовать рекуррентные нейронные сети, но об этом позже

* очень сильно зависит от предметной области
* доминирующие подходы сейчас - эконометрический и нейросетевой

--- 

# Надо пробовать

- [statsmodels](https://www.statsmodels.org/dev/generated/statsmodels.tsa.holtwinters.ExponentialSmoothing.html)
- [fbprophet](https://facebook.github.io/prophet/docs/quick_start.html) 
- [tsfresh](https://tsfresh.readthedocs.io/en/latest/text/quick_start.html)
- [autots](https://winedarksea.github.io/AutoTS/build/html/source/tutorial.html)
- [Darts](https://unit8co.github.io/darts/README.html)
- [Kats](https://github.com/facebookresearch/Kats)
- sktime: [docs](https://sktime.org/) / [Sktime: унифицированная библиотека Python для машинного обучения и работы с временными рядами](https://habr.com/ru/company/otus/blog/511782/)