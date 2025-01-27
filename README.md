# Диффузия

## SD 1.5

- Примерно 20 изображений Гослинга
- Генерировала class_images для регуляризации в другой версии SD, во время обучения выключила генерацию
- включила gradient_checkpointing, иначе не влезало в память
- Взяла 5 промптов, зафиксировала seed и параметры. Результат:

![1](results/forest.jpg)
![1](results/desert.jpg)
![1](results/pool.jpg)
![1](results/cafe.jpg)
![1](results/car.jpg)

## LoRA

- Три эксперимента с параметрами rank = 4, 12, 24
- Поменяла lr, иначе качество было совсем ужасное
- С ростом rank как будто начинает переобучаться, но лица получаются немного более релистичные 

rank             |  Cafe          | Car | Desert | Pool | Forest|
:-----------:|:--------------:|:----------:|:---------------:|:------------------------:|:------------------------:
4|![1](results/cafe_1.jpg)|![1](results/car_1.jpg)|![1](results/desert_1.jpg)|![1](results/pool_1.jpg)|![1](results/forest_1.jpg)|
12|![1](results/cafe_2.jpg)|![1](results/car_2.jpg)|![1](results/desert_2.jpg)|![1](results/pool_2.jpg)|![1](results/forest_2.jpg)|
24|![1](results/cafe_3.jpg)|![1](results/car_3.jpg)|![1](results/desert_3.jpg)|![1](results/pool_3.jpg)|![1](results/forest_3.jpg)|

## Cравнение

Очевидно, Лора хуже. Возможно, это из-за того, что Лора меняет веса и склонна к переобучению. 

## Бонус - ControlNet

Взяла известный мем клоуна (https://img.ixbt.site/live/images/original/04/23/83/2023/03/17/e6577fdd13.jpg), использовала метод с Сanny

Результат: 

![1](results/cnet.jpg)
