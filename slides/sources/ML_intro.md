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
  top: 20px;
  right: 80px;
  height: 70px;
  line-height: 70px;
  margin-bottom: 20px;
  color: #4520ab;
  font-size: 30pt
}
a {
  color: #4520ab;
}
</style>



##  Машинное обучение / Machine learning





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

# Сегодня

- Краткий экскурс в историю 
- Виды задач в машинном обучении 
- Примеры результатов


--- 
<!-- _footer: 📝 [Машинное обучение для людей](https://vas3k.ru/blog/machine_learning/) -->

# Машинное обучение

![h:400 center](https://i.vas3k.ru/7r9.jpg)



---
<!-- _footer: 📝[Arvind Narayanan Twitter](https://twitter.com/random_walker/status/976836626121977858) -->

# Терминология

![h:450 center](https://devhumor.com/content/uploads/images/March2018/tech_buzz_words.png)

---

# Вехи

1805 – метод наименьших квадратов
1812 – теорема Байеса
1913 – марковские цепи
1950e – первые нейросети
1970е – “AI Winter”
1986 – backpropagation (эффективное обучение нейросетей)
1995 – Random Forest, SVM
2012 – «возрождение» нейросетей (AlexNet)

--- 

# Машины побеждают людей 

1979: нарды
1997: шахматы
2008: покер
2011: распознавание дорожных знаков
2013: возраст по фото
2014: распознавание боли
2015: распознавание изображений
2016: го
2016: чтение по губам
2016: распознавание речи

---
<!-- _footer: 📝[Machine Learning vs. Traditional Programming Paradigm](https://datalya.com/blog/machine-learning/machine-learning-vs-traditional-programming-paradigmm) 
-->

# Программирование vs. Машинное обучение

![center h:450](https://datalya.com/blog/content/4-machine-learning/11-machine-learning-vs-traditional-programming-paradigm/ml_vs_traditional_paradigm.png)


---
<!-- _footer: 📝 [Машинное обучение для людей](https://vas3k.ru/blog/machine_learning/) -->

# Типы задач 

![center h:600](https://i.vas3k.ru/7r6.jpg)



--- 
<!-- _footer: 📝[Нейрореволюция в головах и сёлах](https://habr.com/ru/post/277069/)  -->

# Пример: детекция объектов

![center h:400](https://hsto.org/files/035/947/865/035947865b38497e9d2e454f0b3e741b.PNG)


--- 
<!-- _footer: 📝[Raul Pesch, Twitter](https://twitter.com/raulpesch/status/664749621126799360) -->

# Пример: детекция эмоций 

![center h:400](https://pbs.twimg.com/media/CTmqQezWIAA-cD0?format=png&name=medium)


--- 
<!-- _footer: 📝[U-Net: Image Segmentation Network](https://neurohive.io/en/popular-networks/u-net/)  -->

# Сегментация изображений

![center h:400](https://neurohive.io/wp-content/uploads/2018/11/u-net-segmentation-e1542978983391.png)


--- 

<!-- _footer: 📝[Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks](https://junyanz.github.io/CycleGAN/)  -->

# Пример: перенос стиля 

![center h:450](https://junyanz.github.io/CycleGAN/images/objects.jpg)

--- 
<!-- _footer: 📝[Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks](https://junyanz.github.io/CycleGAN/) -->

# Пример: перенос стиля 

![center h:450](https://junyanz.github.io/CycleGAN/images/painting2photo.jpg)
