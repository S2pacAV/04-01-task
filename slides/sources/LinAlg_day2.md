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

  * {
    box-sizing: border-box;
  }
  header {
      height: 675px;
      right: 20px;
      /* margin-bottom: 80px; */
  }
  header img {
      height: 60px;
      float: right;
  }

 /* Выделит области контейнеров, понадобится в случае правки сайтов */
  /* div {
    border: 1px solid black;
  }
  div > div {
    border: 1px solid blue;
  } */

  .container {
    height: 100%;
    overflow: hidden;
  }

  .data-container {
    height: 76%;
    display: flex;
    align-items: center;
  }

  .image-container {
    width: 70%;
    height:100%;
  }

  .table-container {
    margin-left: auto;
    border: 1px solid red;
  }
    .columns {
    display: flex;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
  .columns-left {
  }
  .columns-right {
  }

a {
  color: #4520ab;
}
</style>

# Фаза 1 • Неделя 1 • Вторник 
 
## Линейная алгебра • Linear Algebra

### PCA и SVD

---
# Пониженние размерности с помощью PCA

* __PCA(principal component analysis)__ или иначе говоря - метод главных компонент. Этот алгоритм позволяет перейти от пространств больших размерностей, к пространствам меньших размерностей, пытаясь сохранить ключевую информацию. 

* ниже пример понижения __3D -> 2D__

![center](https://neerc.ifmo.ru/wiki/images/5/5a/800px-Pca_3d_to_2d_example_v2.png)


---
# Пониженние размерности с помощью PCA 

* __2D -> 1D__

![center](https://blog.damavis.com/wp-content/uploads/2021/10/figura1-1.png)

> 🔥`sklearn.decomposition.PCA`


<!-- _footer: ©️📝[PCA animation (Singular Value Decomposition)](aux/pca.gif) -->


---

# Алгоритм понижения размерности PCA

1.Нормировка данных(StandardScaler)
2.Взять матрицу ковариаций
3.Cобственные числа и собственные векторы
4. Взять топ <b>k</b> собственных чисел и соответствующих им собственных векторов
5. Умножить исходную матрицу признаков (<b>mxn * nxk = mxk</b>)
6. Итоговая матрица __mxk__ и есть результат понижения 

---

# Сингулярное разложение матрицы / SVD 

* _SVD_ позволяет разложить одно матричное преобразование __M__ на произведение трех простых $M = U * \Sigma * V$

<div class="columns">
<div class="columns-left">

![center h:420](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bb/Singular-Value-Decomposition.svg/1920px-Singular-Value-Decomposition.svg.png)
</div>

<div class="columns-right">

![center h:420 w:900](aux/svd.png)
</div>

--- 

<!-- _footer: ©️📝[Recommender Systems with Python — Part III: Collaborative Filtering (Singular Value Decomposition)](https://heartbeat.fritz.ai/recommender-systems-with-python-part-iii-collaborative-filtering-singular-value-decomposition-5b5dcb3f242b) -->

# SVD в рекомендательных системах

* Пример применения матричных разложений в рекомендательных системах

![center](aux/svd_recsys.png)


--- 

# SVD в изображениях

![center h:550](aux/svd_image_example.png)
