# Первая лекция, часть 2
## Начала оптимизации

Любая оптимизационная задача это две вещи
- функция, которую мы максимизируем
- область определения аргументов, по которым мы максимизируем

Рассмотрим несколько примеров, в которых хорошо видно, что двумя ключевыми свойствами задачи являются: выпуклость/вогнутость самой функции, а также ограниченность и положение области определения.

::::{prf:example} 
:::{tabbed} A

Парабола рогами вниз на отрезке от -1 до 1

$$ -x^2 \to \max_{x \in [-1,1]}$$ 

Достигает максимума в точке 0.
:::

:::{tabbed}  B

Парабола рогами вниз на отрезке от -2 до -1

$$ -x^2 \to \max_{x \in [-2,-1]}$$ 

Достигает максимума в точке -1.
:::

:::{tabbed} C
 
Парабола рогами вверх на отрезке от -1 до 1

$$ x^2 \to \max_{x \in [-1,1]}$$ 

Достигает максимума в точкax -1 и 1.
:::

:::{tabbed} D

Парабола рогами вверх на отрезке от -1 до 1

$$ x^2 \to \max_{x \in [-1,1]}$$ 

Достигает максимума в точкax -1 и 1.
:::

:::{tabbed} E

Парабола рогами вверх на всей числовой прямой

$$ x^2 \to \max_{x \in \mathbb{R}}$$ 

Не достигает своего максимума, вообще.
:::

:::{tabbed} F

Парабола рогами вверх на интервале от -1 до 1

$$ x^2 \to \max_{x \in \mathbb{R}}$$ 

Также не достигает максимума
:::

::::


### Существование решений

Существование решения, как правило, мы можем легко показать при помощи следующей теоремы

:::{prf:theorem} Вейерштрасса
:class: remark
Непрерывная функция на компакте гарантированно достигает своего минимума и максимума.
:::

Что такое непрерывная функция вы уже знаете. 

A **компакт** в $\mathbb{R}^n$ это просто ограниченное и замкнутое множество. В контексте одномерной оптимизации, $[a,b]$ это компакт, а $(a,b]$, $[a,b)$, $(a,b)$, $[a,\infty)$,$(a,\infty)$ это все не компакты. 

Таким образом, у вас есть всего два сценария как решение оптимизационной задачи с непрерывной функцией могло бы не существовать: либо оно вообще бесконечно, либо оно конечно, но достигается в точке которая попала на границу области.

## Условия первого порядка

Если решение лежит внутри области, то обязательно выполнены условия первого порядка. Например, если функция $U(x, y, z)$ от трех переменных, и вы убедили себя что решение надо искать внутри, то

$$\text{УПП (FOC)}: \quad  \nabla U = 0$$ 

должны выполняться в оптимальной точке $(x^{\ast}, y^{\ast}, z^{\ast})$. Зачастую, граничных точек не так уж и много, и их можно просто перебрать руками, сравнивая значения. Затем можно выбрать наилучшую из граничных и внутренних точек, удовлетворяющих УПП.

## Условия второго порядка

Иногда число кандидатов на оптимум, прошедших условия первого порядка,  можно дополнительно сузить за счет условий второго порядка.

$$\text{УВП (SOC)}: \quad  \nabla^2 U \ ? \ 0$$

Если Гессиан во внутренней точке отрицательно определен $\nabla^2 U \leqslant 0$ (парабола рогами вниз) то это локальный максимум и этот кандидат проходит отбор. Если Гессиан положительно определен $\nabla^2 U \geqslant 0$ (парабола рогами вверх) то это локальный минимум и этот кандидат не проходит отбор.

Если у вас остался один кандидат то он и является оптимумом. Если кандидатов несколько то надо опять сравнивать значения функции руками.

## Выпуклые задачи

К счастью, в экономике, зачастую удается показать что, поверх непрерывности, функция полезности

- либо вогнутая
- либо она монотонное преобразование вогнутой
- либо она квази-вогнутая

Если, вдобавок к этому, область определения не только компакт но и выпуклое множество, то, во первых, решение всегда единственное, а во вторых, условия второго порядка можно не проверять, поскольку они (или что то очень похожее на них) выполнены глобально.

Очень важно уметь, глядя на задачу, определять выпуклая она или нет, чтобы не тратить время на анализ второго порядка. Общий алгоритм решения выпуклых и непрерывных задач на компакте очень простой:

:::{mermaid}

graph TD
F((все выпукло?)) -- no --> G[думаем нестандартно...];
F -- yes --> D;
D[решаем УПП] --> A((она внутри?));
A -- yes --> B[это ответ!];
A -- no --> C[ищем на границе...];

:::

То есть, мы набрасываемся на такую задачу, как будто решение у нее внутреннее. Затем проверяем, что мы не ошиблись. Если кандидат оказался внутри, то это и есть правильный ответ. Если же нет, то мы заново ищем вдоль границы, исходя из геометрических соображений.

## Линии уровня

Наконец, линии уровня это очень удобный инструмент для отлова и классификации кандидатов на решение оптимизационной задачи.

:::{prf:definition}
**Линией уровня** полезности $U$, проходящей через точку $x$ называется множество всех точек $y \in X$ таких что $U(y) = U(x)$.
:::

:::{prf:definition}
**Кривой безразличия** предпочтений $\succcurlyeq$, проходящей через точку $x$ называется множество всех точек $y \in X$ таких что $x \sim y$.
:::

Совершенно ясно, что в контексте представлений предпочтений полезностями и наоборот, кривая безразличия и линия уровня это одно и то же.

Рассмотрим несколько примеров полезностей

::::{prf:example} 


:::{tabbed} Линейная
Рассмотрим полезность вида: $U(x, y) = ax + by$. Тогда линия уровня ищется следующим образом: 

$$
\begin{gather*}
c = ax + by\\
c-ax = by\\
y = \frac{c-ax}{b}
\end{gather*}
$$

Линия уровня это прямая вида $y = \alpha x + \beta$.

:::

:::{tabbed} Гиперболическая
Рассмотрим полезность вида: $U(x, y) = a \log x + \log y$. Тогда линия уровня ищется следующим образом: 

$$
\begin{gather*}
c =  a \log x + \log y\\
e^{c} = x^a y\\
y =\frac{e^{c}}{x^a}
\end{gather*}
$$

Линия уровня это гипербола вида $y = x^\alpha \beta$.

:::

:::{tabbed} Полезность минимум
Рассмотрим полезность вида: $U(x, y) = \min(ax, by)$. Тогда линия уровня ищется следующим образом: 

$$
\begin{gather*}
c = \min(ax, by)\\
\frac{c}{b}= \min(\frac{a}{b}x, y), \quad \frac{c}{a}= \min(x, \frac{b}{a}y)\\
y = \frac{c}{b} \mathbb{I}(ax > c), \quad x = \frac{c}{a} \mathbb{I}(by > c)
\end{gather*}
$$

Линия уровня это конкатенация горизонтальной и вертикальной линий, соединенных вдоль $ax = by$.
:::

::::

### Зачем нужны линии уровня?
Очень часто, в задачах есть выпуклое ограничение типа неравенства, например, бюджетное ограничение. В таком случае, все кандидаты будут формально не внутренние. Однако, с точки зрения выпуклой оптимизации, такие точки можно интерпретировать как "внутренние", если решать методом Лагранжа. О методе Лагранжа мы поговорим на следующей лекции.

Внутреннее решение выпуклой (и гладкой) оптимизационной задачи можно охарактеризовать как точку касания линии уровня с выпуклым ограничением, см. иллюстрацию.

:::{image} ./tangency.png
:alt: Внутреннее решение
:width: 400px
:align: center
:::

Иногда задача вообще не является гладкой, как в случае Леонтьефских полезностей. Тогда линии уровня это самый быстрый и надежный подход к решению задачи. 