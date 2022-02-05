# Семинар 4
*5 февраля 2022. Провела Яна* 🐸

## Задача 1: про налоги

Гусь потребляет картофель и свёклу (везде в задаче предполагайте, что картофель и свёкла измеряются в килограммах). Цена картофеля равна 5 рублей, а свёклы - 10. Доход Гуся равен 50 рублям. Полезность, которую Гусь получает от потребления картофеля ($x$) и свёклы (y), равна 

$$u(x, y)=2\sqrt{x}+y.$$

1. Выпишите бюджетное ограничение Гуся.
2. Запишите оптимизационную задачу Гуся и решите её (необязательно с помощью метода множителей Лагранжа).
3. Предположим, что гуседарство теперь облагает картофель потоварным налогом (вспомните, что это) размером $t$ денежных единиц. Определите, как изменяется в зависимости от ставки $t$ спрос Гуся на картофель и свёклу. 
4. При какой ставке налога $t$ налоговые сборы гуседарства максимальны?
5. Предположим, потоварный налог отменили, но теперь взымается подоходный налог с Гуся в размере $100\cdot \alpha$\%, где $\alpha \in (0, 1)$. Определите, как спрос Гуся на товары зависит от $\alpha$ (можно не приводить вычисления). Как суммарные налоговые сборы зависят от $\alpha$?
6. Гуседарству не понравился эффект от введенного в предыдущем пункте налога, оно отменило его и ввело паушальный налог на доход Гуся. Ответьте на вопросы предыдущего пункта.
 
## Задача 2: про CV и EV (продолжение задачи 1)
*CV - compensating variation, EV - equivalent variation.*

Воспользуемся условием и решением предыдущей задачи, предположив, что доход теперь равен 40.

1. Предположим, стоимость картофеля выросла на 3 денежные единицы. Расчитайте CV и EV. Изобразите на графике.
2. Предположим, стоимость свёклы выросла на 6 денежных единиц. Расчитайте CV и EV. Изобразите на графике.

## Задача 3: про CV и EV на графике функций Хиксианского спроса

Покажите на графике функций спроса по Хиксу компенсирующую вариацию и эквивалентную вариацию. Предполагайте, что у нас два товара, функция полезности $u(x, y)$ вогнутая, бюджетное ограничение линейно, а решение задачи потребителя находится в точке касания кривой безразличия с бюджетным ограничением.

## Задача 4: про IE и SE для разных типов благ

Изобразите на графиках в осях $(x, y)$ для благ $x, y$ эффект дохода и эффект замещения, а также изменение объема потребляемого $x$ при росте цены на благо $x$ (при прочих равных), если $x$:

1. Нормальный товар;
2. Инфериорный товар;
3. Товар Гиффена.

## Задача 5: матрица (уравнение) Слуцкого

<details>
    <summary>Немножко теории</summary>

---
Для начала зададим определение для элемента на $i$-ой строке $j$-том столбце матрицы Слуцкого:

$$s_{ij}=\overbrace{\underbrace{\frac{\partial x_i(p, I)}{\partial p_j}}_{\text{Изменение спроса}} + \underbrace{x_j(p, I)\frac{\partial x_i(p, I)}{\partial I}}_{\text{Эффект дохода}}}^{\text{Эффект замещения}}.$$

Матрица Слуцкого, таким образом, это $S=\{s_{ij}\}_{i,j\in \overline{1, n}}$. С таким определением перед глазами проще работать далее. 

В частности, есть такая сущность, как "декомпозиция Слуцкого" (на английском называют Slutsky decomposition или Slutsky equation). Тут надо просто перенести эффект дохода направо и получим:

$$\frac{\partial x_i(p, I)}{\partial p_j} = s_{ij}-x_j(p, I)\frac{\partial x_i(p, I)}{\partial I}=\frac{\partial h_i(p, u)}{\partial p_j}-x_j(p, I)\frac{\partial x_i(p, I)}{\partial I}.$$

Последний переход к производной хиксианского спроса валиден потому, что элемент $s_{ij}$ матрицы Слуцкого представляет собой эффект замещения, а он, в свою очередь, равен производной хиксианского спроса.

А теперь можно перейти к решению задачи.

---
</details>

Полезность Мопса имеет вид $u(x, y)=\sqrt{x}+y$. Цены благ $x, y$, корм и собачье пиво соответственно, равны $p, q$ соответственно. Доход Мопса (его хозяйки) равен $I$.

1. Выведите функции маршалианского спроса Мопса на корм и пиво ($x, y$). 
2. Выпишите косвенную функцию полезности, $v(p, q, I)$, и функцию расходов, $e(p, q, u)$.
3. Выпишите функции хиксианского спроса Мопса на корм и пиво, $h_x(p, q, u), h_y(p, q, u)$.
4. Выпишите уравнение (декомпозицию) Слуцкого. Являются ли товары субститутами?
5. Выпишите матрицу Слуцкого.
6. Дайте характеристику благам $x, y$ (комплементы/субституты, нормальные/инфериорные).

## Задача 6: про IE и SE для квазилинейной функции полезности

<details>
    <summary>Почему так много квазилинейных функций?</summary>

---
Это один из самых распространенных видов функций в экономике, если не самый. С ней очень удобно работать, а дополнительное удобство доставляет отсутствие эффекта дохода.

---

</details>

Давайте покажем, что следующее утверждение верно:

:::{prf:property}
Квазилинейная функция полезности

$$u(x, y)=f(x)+ky,$$

где $f(\cdot)$ - вогнутая функция, характеризуется отсутствием эффекта дохода при рассмотрении блага $x$.
:::