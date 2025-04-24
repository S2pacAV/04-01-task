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

a {
  color: #4520ab;
}
</style>

# Фаза 1 • Неделя 1 • Понедельник 
 
## Линейная алгебра • Linear Algebra


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

# Вектор

**Вектор** – элемент векторного пространства с произвольной размерностью по одному из измерений. 

Заданы два вектора: 

$$\overrightarrow{A} = (a_{1}, a_{2}, a_{3});  \overrightarrow{B} = (b_{1}, b_{2}, b_{3})$$

- сумма векторов $\overrightarrow{A} + \overrightarrow{B} = (a_{1} + b_{1}, a_{2} + b_{2}, a_{3} + b_{3})$ </br>

- разность векторов: $\overrightarrow{A} - \overrightarrow{B} = (a_1 - b_1, a_2 - b_2, a_3 - b_3)$ </br>

- произведение вектора $\overrightarrow{A}$ на число $\lambda$: $\lambda \overrightarrow{A} = (\lambda a_1, \lambda a_2, \lambda a_3)$


--- 

# Вектор

Длина (норма) вектора $\overrightarrow{A} = (a_1, a_2, a_3)$ обозначается $|\overrightarrow{A}|$ и вычисляется: 
$$|\overrightarrow{A}| = \sqrt{a_1^2 + a_2^2 + a_3^2}$$ 



Скалярное произведение векторов $\overrightarrow{A}$ и $\overrightarrow{B}$:
$$(\overrightarrow{A}, \overrightarrow{B}) = |\overrightarrow{A}| \boldsymbol{\cdot} |\overrightarrow{B}| \boldsymbol{\cdot} \cos\angle(\overrightarrow{A}, \overrightarrow{B})$$

$$ \cos\angle (\overrightarrow{A}, \overrightarrow{B}) = \dfrac{a_1b_1 + a_2b_2 + a_3b_3}{\sqrt{a_1^2 + a_2^2 + a_3^2} \cdot \sqrt{b_1^2 + b_2^2 + b_3^2}}$$


--- 
# Вектор 

Если векторы даны в координатах:
$$ (\overrightarrow{A}, \overrightarrow{B}) = \sum_{i=1}^{n} a_i b_i $$

Если $|\overrightarrow{A}| \neq 0, |\overrightarrow{B}| \neq 0$, скалярное произведение равно нулю только в случае перпендикулярности векторов: 
$$(\overrightarrow{A}, \overrightarrow{B}) = 0 \iff \overrightarrow{A} \perp \overrightarrow{B}$$

--- 

<!-- _footer:  📝 [Questions & Answers](https://www.vedantu.com/question-answer/if-a-and-b-are-two-non-collinear-vectors-and-xy-class-12-maths-cbse-5f83028d781fe74044c327e5) -->

# Коллинеарные вектора 
Векторы называются коллинеарными, если они лежат на одной или на параллельных прямых:

![center h:300](https://www.vedantu.com/question-sets/5d4c1bfa-453e-44aa-a13e-3cad71baf5161635162461965615887.png)

<!-- ---

# Компланарность векторов
 - Любые векторы, лежащие на одной плоскости или параллельные одной плоскости, называются **компланарными**. 
 - Три вектора называются **компланарными**, если они при приведении к общему началу лежат в одной плоскости.  


Какие векторы на рисунке компланарны?
![center h:300](https://ykl-res.azureedge.net/2c71797b-6fe3-4a4e-b08e-eda2940b651e/Vektoru_veidi.png)

---

# Компланарность векторов 



**Формально**: пусть векторы $\overrightarrow{a}$ и $\overrightarrow{b}$ неколлинеарны. Если для вектора $\overrightarrow{c}$ существует единственная пара реальных чисел $x$ и $y$, такая, что $\overrightarrow{c} = x \cdot \overrightarrow{a} + y \cdot \overrightarrow{b}$, то векторы $\overrightarrow{a}, \overrightarrow{b}, \overrightarrow{c}$ компланарны. 
Если три вектора $\overrightarrow{a}, \overrightarrow{b}, \overrightarrow{c}$ компланарны и векторы $\overrightarrow{a}, \overrightarrow{b}$ не коллинеарны, то вектор $\overrightarrow{c}$ можно **разложить** по векторам $\overrightarrow{a}, \overrightarrow{b}$ только одним образом.


--- 

# Компланарность векторов 

$\overrightarrow{AC} =  \overrightarrow{AB} + \overrightarrow{AD} = x \cdot \overrightarrow{AA}_{1} + y \cdot \overrightarrow{AA}_{2}$

![center](https://ykl-res.azureedge.net/2604363e-13dd-4eab-ba94-041c2db49778/Komplanari_vekt.png) -->


---

# Базис

**Базис** – такой набор векторов в пространстве, что любой вектор этого пространства может быть единственным образом представлен в виде линейной комбинации векторов из этого набора. 

![center h:400](https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Basis_graph_%28no_label%29.svg/1024px-Basis_graph_%28no_label%29.svg.png)


--- 

# Матрицы

$$
\begin{pmatrix}
a_{11} & a_{12}  & \dots  & a_{1n}\\ 
a_{21} & a_{22} & \dots & a_{2n}\\ 
\dots & \dots & \dots & \dots \\ 
a_{m1} & a_{m2} & \dots & a_{mn}
\end{pmatrix}
$$

---

# Матрицы

- если $m = n$, то матрица квадратная

$
\begin{pmatrix}
a_{11} & a_{12}  & a_{13}\\ 
a_{21} & a_{22} & a_{23} \\ 
a_{31} & a_{22} & a_{33}
\end{pmatrix}
$

- если все элементы матрицы равны нулю, то матрица нулевая
$0_1 = |0|, 0_2 = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}$
- если элементы главной диагонали матрицы равны 1, а остальные нулю, то матрица едничиная
$
I_1=
\begin{pmatrix}
1 & 0  \\ 
0 & 1  \\ 
\end{pmatrix}
I_3=
\begin{pmatrix}
1 & 0  & 0\\ 
0 & 1 & 0 \\ 
0 & 0 & 1
\end{pmatrix}
$

---

<!-- _footer: 📝[Essential Math for Data Science: Introduction to Matrices and the Matrix Product](https://www.kdnuggets.com/2021/02/essential-math-data-science-matrices-matrix-product.html) -->

# Операции над матрицами

![center](https://hadrienj.github.io/assets/images/ch07_matrices/ch07_matrix_vector_dot_product.png)

--- 


# Операции над матрицами


$$ 
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix} \bullet 
\begin{pmatrix}
x  \\
y 
\end{pmatrix} = 
\begin{pmatrix}
ax + by \\
cx + dy
\end{pmatrix}
$$

$$ 
C = 
\begin{pmatrix}
1 & 2 \\ 
3 & 4 
\end{pmatrix}
D = 
\begin{pmatrix}
5 \\ 
7  
\end{pmatrix}
$$


$$
C \boldsymbol{\cdot} D = ?
$$

---

<!-- _footer: 📝[Essential Math for Data Science: Introduction to Matrices and the Matrix Product](https://www.kdnuggets.com/2021/02/essential-math-data-science-matrices-matrix-product.html) -->

# Операции над матрицами

![center h:400](https://hadrienj.github.io/assets/images/ch07_matrices/ch07_matrix_matrix_dot_product.png)

--- 
# Операции над матрицами

$$ 
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix} \bullet 
\begin{pmatrix}
w & x \\
y & z
\end{pmatrix} = 
\begin{pmatrix}
aw + by & ax + bz \\
cw + dy & cx + dz
\end{pmatrix}
$$

$$ 
P = 
\begin{pmatrix}
1 & 2 \\ 
3 & 4 
\end{pmatrix}
M = 
\begin{pmatrix}
5 & 6 \\ 
7 & 8 
\end{pmatrix}
$$
</br>

$$
P \boldsymbol{\cdot} M = ?
$$

---

<!-- _footer: 📝[Essential Math for Data Science: Introduction to Matrices and the Matrix Product](https://www.kdnuggets.com/2021/02/essential-math-data-science-matrices-matrix-product.html) -->

# Операции над матрицами

![center h:450](https://hadrienj.github.io/assets/images/ch07_matrices/ch07_reverse_rule_transpose.png)

--- 

# Операции над матрицами

$$ 
P = 
\begin{pmatrix}
1 & 2 \\ 
3 & 4 
\end{pmatrix}
I_2 = 
\begin{pmatrix}
1 & 0 \\ 
0 & 1 
\end{pmatrix}
$$


$$
P \boldsymbol{\cdot} I_2 = ?
$$

---

# Определитель матрицы / Determinant

Определитель матрицы важен для вычисления обратной матрицы, скалярная величина, вычисляемая для **квадратных матриц** размера $n \times n, n \geq 1$: 
$$
n = 1: \Delta = |a_{11}| = a_{11}
$$

$$
n = 2: \Delta = \begin{vmatrix} a & c \\ b & d \end{vmatrix} = ad - bc
$$


---

# Определитель матрицы

$$
n = 3: 
\Delta = \begin{vmatrix} 
a_{11} & a_{12} & a_{13} \\ 
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{vmatrix} = 
a_{11} \begin{vmatrix} a_{22} & a_{23} \\ a_{32} & a_{33} \end{vmatrix} - 
a_{12} \begin{vmatrix} a_{21} & a_{23} \\ a_{31} & a_{33} \end{vmatrix} + 
a_{13} \begin{vmatrix} a_{21} & a_{22} \\ a_{31} & a_{32} \end{vmatrix} = \\
\\
a_{11}a_{22}a_{33} - a_{11}a_{23}a_{32} - a_{12}a_{21}a_{33} + a_{12}a_{23}a_{31} + a_{13}a_{21}a_{32} - a_{13}a_{22}a_{31}
$$

---

# Правило Саррюса

![center h:400](https://upload.wikimedia.org/wikipedia/commons/thumb/1/17/Determinant-sarrus.svg/333px-Determinant-sarrus.svg.png)

---

# Определитель матрицы 

$$
\Delta = \begin{vmatrix} 
a_{11} & a_{12} & a_{13} \\ 
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{vmatrix} = 
a_{11} \begin{vmatrix} a_{22} & a_{23} \\ a_{32} & a_{33} \end{vmatrix} - 
a_{12} \begin{vmatrix} a_{21} & a_{23} \\ a_{31} & a_{33} \end{vmatrix} + 
a_{13} \begin{vmatrix} a_{21} & a_{22} \\ a_{31} & a_{32} \end{vmatrix} = \\
a_{11}a_{22}a_{33} - a_{11}a_{23}a_{32} - a_{12}a_{21}a_{33} + a_{12}a_{23}a_{31} + a_{13}a_{21}a_{32} - a_{13}a_{22}a_{31}
$$
<br />

$$
\Delta = 
\begin{vmatrix} 
1 & -2 & 3 \\ 
4 & 0 & 6 \\
-7 & 8 & 9
\end{vmatrix} = ?
$$

<!-- --- 

# Определитель матрицы

У определителя матрицы много [свойств](https://ru.wikipedia.org/wiki/%D0%9E%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B8%D1%82%D0%B5%D0%BB%D1%8C#%D0%9E%D1%81%D0%BD%D0%BE%D0%B2%D0%BD%D1%8B%D0%B5_%D1%81%D0%B2%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%B0_%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B8%D1%82%D0%B5%D0%BB%D0%B5%D0%B9), самые важные такие: 

1. $\det I = 1$
2. $\det A^T = \det A$
3. $\det (AB) = \det A \cdot \det B$ -->

---

# Элементарные преобразования матриц

__Элементарные преобразования матрицы__ — это такие преобразования матрицы, в результате которых сохраняется эквивалентность матриц. Таким образом, элементарные преобразования не изменяют множество решений системы линейных алгебраических уравнений, которую представляет эта матрица.

Элементарными преобразованиями строк называют:

* перестановку местами любых двух строк матрицы;
* умножение любой строки матрицы на константу $k, k\neq 0$, при этом определитель матрицы увеличивается в $k$ раз;
* прибавление к любой строке матрицы другой строки, умноженной на некоторую константу.

---

# Обратная матрица  / Inverse matrix
Матрица $M^{-1}$ является обратной для матрицы $M$ размера $n \times n$ когда выполняется условие: 

$$
M \boldsymbol{\cdot} M^{-1} = I_n
$$

--- 

# Обратная матрица через присоединенную

Дано: $A  = \begin{pmatrix} 7 & 4 \\
5 & 3 
\end{pmatrix}$

Дополняем единичной матрицей справа: 
$A \mid I  \approx \Big( \begin{matrix} 7 & 4 \\
5 & 3 
\end{matrix} \; \Big| \;
\begin{matrix} 1 & 0 \\
0 & 1 
\end{matrix} \Big)$

От первой строки отнимаем вторую: 
$A \mid I  \approx \Big( \begin{matrix} 2 & 1 \\
5 & 3 
\end{matrix} \; \Big| \;
\begin{matrix} 
1 & -1 \\
0 & 1 
\end{matrix} \Big)$

От второй строки отнимаем две первых: 
$A \mid I  \approx \Big( \begin{matrix} 2 & 1 \\
1 & 1 
\end{matrix} \; \Big| \;
\begin{matrix} 
1 & -1 \\
-2 & 3 
\end{matrix} \Big)$

---

Первую и вторую строки меняем местами: 
$A \mid I  \approx \Big( \begin{matrix} 1 & 1 \\
2 & 1 
\end{matrix} \; \Big| \;
\begin{matrix} 
-2 & 3 \\
1 & -1 
\end{matrix} \Big)$

От второй строки отнимаем две первых: 

$A \mid I  \approx \Big( \begin{matrix} 1 & 0 \\
0 & 1 
\end{matrix} \; \Big| \;
\begin{matrix} 
3 & -4 \\
-5 & 7 
\end{matrix} \Big)$

$A^{-1} = \begin{pmatrix} 3 & -4 \\ -5 & 7\end{pmatrix}$

--- 

<!-- --- # Обратная матрица с помощью союзной матрицы

Матрица $\tilde{A}$ является союзной к квадратной матрице $A$, если элементы матрицы $\tilde{A}$ равны алгебраическим дополнениям соответствущих элементов матрицы $A$. 

$$
A \cdot \tilde{A}^T = |A| \cdot I
$$

Если $|A| \neq 0$, то $A \cdot \tilde{A}^T \cdot \dfrac{1}{|A|} = I$, тогда 
$$A^{-1} = \dfrac{1}{|A|} \cdot{\tilde{A}^T}$$



# !!!Обратная матрица с помощью союзной матрицы

Вычисление обратной матрицы с помощью союзной. 

$$A =
\begin{pmatrix}
1 & 0 & 2 \\ 
2 & -1 & 1 \\ 
1 & 3 & -1
\end{pmatrix}
$$

$|A| = 1 * (-1) * (-1) + 2 * 3 * 2 + 0 * 1 * 1 - 1 * (-1) * 2 - 3 * 1 * 1 - 2 * 0 * (-1) = 12$

Вычисление алгебраических дополнений (элементов матрицы $\tilde{A}$):  

--- -->

# Ранг матрицы / Matrix rank

**Ранг матрицы** – максимальное число линейно независимых строк. 

1. Ранг нулевой матрицы (вектора) равен нулю 
2. Ранг любой матрицы, содержащей хотя бы один ненулевой элемент, не меньше единицы
3. Транспонирование не влияет на ранг 
4. Ранг матрицы всегда не больше ее минимальной размерности 


--- 

# Ранг матрицы / Matrix rank

### Пример
$$
A = \begin{pmatrix}
1 & -1 & 2 \\ 
2 & -2 & 4 \\ 
-1 & 1 & -2
\end{pmatrix}
$$
$rank A = ?$

$$
B = 
\begin{pmatrix} 
1 & -1 & 2 \\ 
0 & 1 & -1
\end{pmatrix}
$$

$rank B = ?$

--- 

# Ранг матрицы / Matrix rank

### Пример
$$
A = \begin{pmatrix}
1 & -1 & 2 \\ 
2 & -2 & 4 \\ 
-1 & 1 & -2
\end{pmatrix}
$$
$rank A = 1$, т.к. все строки матрицы линейно зависимы. 

$$
B = 
\begin{pmatrix} 
1 & -1 & 2 \\ 
0 & 1 & -1
\end{pmatrix}
$$

$rank B = 2$, т.к. строки матрицы линейно независимы.

<!-- --- 

# Минор матрицы

**Минор** матрицы – определитель матрицы, составленный из чисел, находящихся на пересечении различных строк и столбцов. 

> Ранг матрицы равен максимальному порядку ненулевого минора

$$
\begin{pmatrix} 
1 & -1 & 7 & -5 & 3 \\ 
2 & 5 & \mathbf{-3} & 9 & \mathbf{4} \\ 
3 & -2 & 8 & 1 & 5 \\ 
4 & 6 & \mathbf{-4} & 2 & \mathbf{6}
\end{pmatrix} 
$$

$M_2 = 
\begin{vmatrix} 
-3 & 4 \\ 
-4 & 6
\end{vmatrix}
$ -->

<!-- --- 

# Ранг матрицы

$
A = 
\begin{pmatrix}
1 & 2 & 0 & 5 \\ 
2 & 4 & -1 & 0 \\ 
-2 & -4 & 1 & 0 \\ 
1 & 0 & 2 & 1
\end{pmatrix}
$

$M_2 = 
\begin{vmatrix} 
1 & 2 \\ 
2 & 4
\end{vmatrix}=0 \rightarrow
\begin{vmatrix} 
1 & 0 \\ 
2 & -1
\end{vmatrix}=-1 \Rightarrow rank A \geq 2
$

$
M_3 = 
\begin{vmatrix} 
1 & 2 & 0 \\ 
2 & 4 & -1 \\ 
1 & 0 & 2
\end{vmatrix} = -2 \Rightarrow rank A \geq 3
$ -->

---

# Линейные операторы

В пространстве $\mathit{L}$ линейный оператор $\mathbf{A}$, если каждому вектору $x$ из пространства $L$ поставлен в соответствие вектор $\mathbf{A}x$ из $L$:

$$\mathbf{A}(x+y) = \mathbf{A}x + \mathbf{A}y$$
 
 
--- 
<!-- _footer: ©️[A Geometrical Understanding of Matrices](http://gregorygundersen.com/blog/2018/10/24/matrices/) 📊[Linear Transformation Visualizer - Inspired by 3Blue1Brown](https://shad.io/MatVis/)-->

# Линейные операторы

Диагональ паралеллограмма, построенного на векторах $x, y$ при линейном преобразовании $\mathbf{A}$ переходит в диагональ паралеллограмма, построенного на векторах $\mathbf{A}x$ и $\mathbf{A}y$. 

![center h:300](http://gregorygundersen.com/image/matrices/transformation.png)

 

--- 
<!-- _footer:  📊[Linear Transformation Visualizer - Inspired by 3Blue1Brown](https://shad.io/MatVis/)-->

# Линейные операторы

![center h:900](https://mathinsight.org/media/image/source/linear_transformation_2d_m1_m1_1_3.svg)


--- 
<!-- _footer:  📊[Linear Transformation Visualizer - Inspired by 3Blue1Brown](https://shad.io/MatVis/)-->

# Линейные операторы

![center h:400](https://mathinsight.org/media/image/image/linear_transformation_2d_m2_0_0_m2.png)

--- 




Предположим, существует линейный оператор 
$$\mathbf{A}(v) = 2v$$

Его можно записать в матричном виде. Если есть базис $e_1=\begin{pmatrix}1 \\ 0 \end{pmatrix}, \; e_2=\begin{pmatrix}0\\ 1\end{pmatrix}$ в двумерном пространстве, применяем оператор к базисным векторам: 
 - $\mathbf{A}(e_1) = 2\begin{pmatrix}1 \\ 0 \end{pmatrix} \rightarrow \mathbf{A} = \begin{pmatrix} 2 & * \\ 0 & * \\\end{pmatrix}$ 
 
 - $\mathbf{A}(e_2) = 2\begin{pmatrix}0 \\ 1 \end{pmatrix} \rightarrow \mathbf{A} = \begin{pmatrix} 2 & 0 \\ 0 & 2 \\\end{pmatrix}$

--- 

- Дан вектор $c = \begin{pmatrix}-1 \\ 3 \end{pmatrix}$, матрица линейного преобразования $\mathbf{A}(v) = 2v$ 

Решение: 

$\mathbf{A}(c) = \begin{pmatrix} 2 & 0 \\ 0 & 2 \\\end{pmatrix}
                 \begin{pmatrix} -1 \\ 3 \\\end{pmatrix} = 
                 \begin{pmatrix} -2 \\ 6 \\\end{pmatrix}$

--- 

$\mathbf{A}(v) = kv$ –  преобразование подобия:
 - если $k > 1$, то объект растягивается в $k$ раз
 - если $0 < k < 1$, то объект сжимается в $k$ раз
 - если $k=1$, то преобразование тождественно
 - если $k < 0$, то ?

---

Что произойдет с объектом, если применить к нему следующие преобразования:

 - $\mathbf{A}_1 = \begin{pmatrix} 0.3 & 0 \\ 0 & 1 \end{pmatrix}$
 - $\mathbf{A}_2 = \begin{pmatrix} 1 & 0 \\ 0 & 1.5 \end{pmatrix}$
 - $\mathbf{A}_3 = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$
 - $\mathbf{A}_4 = \begin{pmatrix} \cos\alpha & -\sin\alpha \\ \sin\alpha & \cos\alpha \end{pmatrix}$

