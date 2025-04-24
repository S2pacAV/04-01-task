---
marp: true


# Define title slide
_class: invert
_backgroundColor: #4520ab;
_paginate: skip;
_footer: 
# _header: "![](https://elbrusboot.camp/static/newLogo-00ed4b8011624cd94aa1812d35f25088.svg)"

math: katex
---

<style>
img[alt~="center"] {
  display: block;
  margin: 0 auto;
}
h1 {
  position: absolute;
  left: 77px;
  top: 20px;
  right: 80px;
  height: 70px;
  line-height: 70px;
  margin-bottom: 20px;
  color: #4520ab;
  font-size: 28pt
}

h3 {
  position: absolute;
  left: 70px;
  top: 60px;
  font-size: 17pt;
  /* right: 80px; */
  /* height: 70px; */
  /* line-height: 70px; */
  /* margin-bottom: 20px; */
  color: black; 
  font-style: normal;
}

a {
  color: #4520ab;
}

  .container {
    height: 100%;
    overflow: hidden;
  }

  .data-container {
    height: 73%;
    display: flex;
    align-items: center;
  }

  .image-container {
    width: 49%;
    height:100%;
  }

  .table-container {
    
  }

</style>

# Фаза 1 • Неделя 2 • Среда

## Производные и градиентный спуск • Gradient descent
---
<!--- backgroundColor: white --->
<!--- paginate: true --->
<!-- header: "![](aux/Elbrus-bootcamp-RU.png)" -->

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

# Производная функции

**Производная функции** характеризует скорость изменения функции в данной точке. 

**Через предел:** производной функции $f$ в точке $x_0$ называется предел:

$$f'(x_0) = \lim_{x \rightarrow x_0} \dfrac{f(x) - f(x_0)}{x - x_0} = \lim_{\Delta x \rightarrow 0} \dfrac{f(x_0 + \Delta x) - f(x_0)}{\Delta x} = \lim_{\Delta x \rightarrow 0}\dfrac{\Delta f(x)}{\Delta x}$$


--- 
# Производная функции

**Производная функции** характеризует скорость изменения функции в данной точке. 

**Через предел:** производной функции $f$ в точке $x_0$ называется предел:

$$f'(x_0) = \lim_{x \rightarrow x_0} \dfrac{f(x) - f(x_0)}{x - x_0} = \lim_{\Delta x \rightarrow 0} \dfrac{f(x_0 + \Delta x) - f(x_0)}{\Delta x} = \lim_{\Delta x \rightarrow 0}\dfrac{\Delta f(x)}{\Delta x}$$

**Геометрически:** если функция $f$ имеет конечную производную в точке $x_0$, то ее можно приблизить линейной функцией: 

$$f_l(x) = f(x_0) + f'(x_0)(x-x_0)$$

Тогда функция $f_l$ называется *касательной* к $f$ в точке $x_0$, а число $f'(x_0)$ является *тангенсом* угла наклона касательной прямой. 

---

# Производная функции

![center h:500](https://avatars.dzeninfra.ru/get-zen_doc/3952637/pub_5f4559d569db446e269a80e1_5f457599cd42f3302e7fdd34/scale_1200)

--- 
# Элементарные производные




||||
|-|-|-|
|$c' = 0, c = const$    | $\ln x = \dfrac{1}{x}$ | $(\log_a x)' = \dfrac{1}{x \ln a}$ |
|$(x^n)' = nx^{n-1}$    | $(\sin x)' = \cos x$   | $\tg x = \dfrac{1}{\cos^2 x}$ |
|$(a^x)'= a^x \ln a$    | $(\cos x)' = - \sin x$ | $(\sqrt{x})' = \dfrac{1}{2 \sqrt{x}}$
|$(e^x)' = e^x$         ||


--- 

# Свойства производных

1. $(f(x) + g(x))' = f'(x) + g'(x)$
2. $(f(x) - g(x))' = f'(x) - g'(x)$
3. $(f(x)g(x))' = f'(x)g(x) + f(x)g'(x)$
4. $(C f(x))' = C f'(x)$
5. $\left( \dfrac{f(x)}{g(x)} \right)' = \dfrac{f'(x)g(x) - f(x)g'(x)}{g^2(x)}$

---

# Производная сложной функции

Пусть $y$ - сложная функция, т.е. $y = f(u),  u = g(x)$. Если обе функции дифференцируемые, то сложная функция тоже дифференцируема в точке $x$ и производная в точке равна: 

$$y'(x) = f'(u)g'(x)$$

---

# Производная сложной функции

Пусть $y$ - сложная функция, т.е. $y = f(u),  u = g(x)$. Если обе функции дифференцируемые, то сложная функция тоже дифференцируема в точке $x$ и производная в точке равна: 

$$y'(x) = f'(u)g'(x)$$

Пример: $y = \tg{x^2}$. 

Что здесь $f(u)$ и $g(x)$?

Какая производная? 

---

# Производная сложной функции

Пусть $y$ - сложная функция, т.е. $y = f(u),  u = g(x)$. Если обе функции дифференцируемые, то сложная функция тоже дифференцируема в точке $x$ и производная в точке равна: 

$$y'(x) = f'(u)g'(x)$$

Пример: $y = \tg{x^2}$. 

$f(u) = \tg{u}$ \; $g(x) = x^2$

$$y' = \dfrac{1}{\cos^2 x^2} \times (x^2)' = \dfrac{2x}{\cos^2 x^2}$$





---

# Найти производную сложной функции

$$y = \arctg^2 x^3$$

$$ y' = \; ? $$

--- 

# Найти производную сложной функции

$$y = \ln \cos^2 (\sin \sqrt{x}) $$

$$ y'=\; ?$$

--- 
# Найти производную функции

<div class = "container">
<div class="text">

$\sigma (x)$ - Одна из самых часто встречаемых в машинном и глубоком обучении

</div> 

</div> 
  <div class="data-container">
    <div class="image-container">
      <img src="https://www.researchgate.net/publication/358908601/figure/fig6/AS:1132634126200844@1647052427448/Sigmoid-activation-function-and-its-derivative.png" height=100%, width=100%> 
      <img/>
    </div>
    <div class="table-container">
    
$$\sigma (x) = \dfrac{1}{1 + e^{-x}}$$

$$\sigma' (x) = \; ?$$


  </div>
</div> 

---

# Найти производную функции

* Сигмоида 

$$\sigma (x) = \dfrac{1}{1 + e^{-x}}$$

$$\sigma' (x) = \dfrac{e^{-x}}{(1 + е^{-x})^2} $$

Еще ее часто выражают таким образом: 
$$\dfrac{d}{dx} \sigma(x) =\sigma(x) (1-\sigma(x))$$

--- 

# Найти производную функции

$$
\begin{aligned}
\dfrac{d}{dx} \sigma(x) &= \dfrac{d}{dx} \left[  \dfrac{1}{1+e^{-x}} \right] =\dfrac{d}{dx}(1+e^{-x})^{-1} \\
&=-1*(1+e^{-x})^{-2}(-e^{-x}) 
=\dfrac{-e^{-x}}{-(1+e^{-x})^{2}} 
=\dfrac{e^{-x}}{(1+e^{-x})^{2}} \\
&=\dfrac{1}{1+e^{-x}}  \dfrac{e^{-x}}{1+e^{-x}} 
=\dfrac{1}{1+e^{-x}}  \dfrac{e^{-x} + (1 - 1)}{1+e^{-x}} \\
&=\dfrac{1}{1+e^{-x}}  \dfrac{(1 + e^{-x}) - 1}{1+e^{-x}} 
=\dfrac{1}{1+e^{-x}}  \left[ \dfrac{(1 + e^{-x})}{1+e^{-x}} - \dfrac{1}{1+e^{-x}} \right] \\
&=\dfrac{1}{1+e^{-x}}  \left[ 1 - \dfrac{1}{1+e^{-x}} \right] 
=\sigma(x) (1-\sigma(x)) 
\end{aligned}
$$

Если кому-то интересно, почему ее можно выразить по-другому. 



<!-- --- 

# Неопределенный интеграл

Дана функция действительной переменной $f(x)$. Неопределенным интегралом функции (первообразной) называется функция  $F(x)$, производная которой равна $f(x)$: $F'(x) = f(x)$. 

$$F(x) = \int{}f(x) dx $$

Производные функций, отличающихся на константу, совпадают, потому в интегралы подставляют произвольную постоянную $C$. 

--- 

# Определенный интеграл

![center h:550](https://upload.wikimedia.org/wikipedia/commons/thumb/7/78/Integral-R1.svg/600px-Integral-R1.svg.png)

При $\max \Delta x_i \rightarrow 0,  \; S = \sum_{i=0}^{n-1} y_i \Delta x_i \rightarrow \int_{a}^{b} f(x) dx$

--- 

# Метод замены переменной

Найти значение неопределенного интеграла $\int \sin(3x + 1)dx$. Ближайшее табличное значение интеграла для этого случая $\int \sin x dx = - \cos x + C$. Необходимо получить значение $3x + 1$ под знаком дифференциала: 

$d(3x + 1) = (3x+1)'dx = 3dx$. 

Итог: $\int \sin (3x+1)dx = \dfrac{1}{3} \int \sin (3x+1)d(3x+1) = -\dfrac{1}{3}\cos (3x+1) + C$

--- 

# Метод замены переменной

Найти неопределенный интеграл: 
$$\int \dfrac{dx}{5 - 2x}$$

Табличный интеграл: 
$$\int \dfrac{dx}{x} = \ln |x| + C$$

Подводим $5 - 2x$ под знак интеграла и вычисляем: 
$$\int \dfrac{dx}{5 -2x} = -\dfrac{1}{2} \int \dfrac{d(5-2x)}{5-2x} = -\dfrac{1}{2} \ln |5-2x| + c$$ -->

---

# Градиентный спуск

* Дифференцирование используется для минимизации функции по параметрам
* Рассмотрим пример: 

$$L(w) = w^2 + 12$$

* Производная функции: 

$$ \dfrac{\partial L}{\partial w} = 2w$$

* Эта функция очень простая, мы можем найти ее минимум аналитически
* Но мы воспользуемся процедурой градиентного спуска для поиска минимума по параметру $w$

--- 
<!-- _footer: 📊[Let's play with gradient descent](https://uclaacm.github.io/gradient-descent-visualiser/#playground) -->
# Градиентный спуск

### Общий алгоритм

* Дана функция $L(w)$, надо найти значение параметра $w$, при котором значение функции будет минимальным: $L(w) \rightarrow \min_{w}$, $w_0$ = random
* Производная функции по параметру $w$ равна $\dfrac{\partial L}{\partial w}$
* На каждой итерации обновляем значение параметра $w$ по правилу: 
$$w_{i+1} = w_i - \lambda \dfrac{\partial L}{\partial w}$$
  * $\lambda$ - скорость обучения (`learning_rate`)
* Вычисляем значение $L(w_{i+1})$
* Останавливаемся, если $|L(w_{i+1}) - L(w_{i})| < \epsilon$, $\epsilon$ - параметр (напр., 0.01)

---
# Градиентный спуск

![center h:500 w:800](https://miro.medium.com/v2/resize:fit:1200/1*iNPHcCxIvcm7RwkRaMTx1g.jpeg)

---

# Итоги

* на основе итеративной процедуры корректировки параметров работает много алгоритмов машинного обучения
* градиент - вектор частных производных по каждому параметру
* у обычного градиентного спуска есть проблемы, для алгоритмов в машинном обучении используются более сложные варианты