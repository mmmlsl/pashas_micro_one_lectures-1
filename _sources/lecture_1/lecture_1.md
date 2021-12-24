# План и цели лекции

Сегодня мы поговорим о моделях поведения потребителя. 

**Первая часть лекции** посвящена моделям в целом и зачем они нужны. Мы поговорим о двух классических моделях поведения, которые можно охарактеризовать грубо как:

- **полезность** (классическая модель)
- **предпочтение** (нео-классическая модель)

Будет также третья модель, модель **выбора**, вы увидите ее на семинаре и в домашке. Это продвинутый материал, его надо частично самостоятельно изучить по учебнику БЖЦ.

У каждой модели будет свой набор аксиом. Мы обсудим, как эти модели связаны друг с другом, а также потренируемся в их формализме на примерах. Важную часть в этой лекции будет занимать **Теорема Дебре**, связывающая полезность и предпочтения. В центре этой теоремы лежит понятие **непрерывности**, которое вам придется освоить. Формулировку этой теоремы придется выучить.

**Вторая часть лекции** посвящена началам оптимизации, которой вам придется активно пользоваться в этом курсе. Особое внимание будет уделено понятию **выпуклости**. Ожидается, что вы научитесь отличать выпуклые задач от не выпуклых, что сильно облегчит вам жизнь в будущем.

# Литература

- **Вариан, 1.1-1.5** доступно о моделировании, спросе, оптимизации и равновесии
- **Вариан, 3.1-3.4** доступно о предпочтениях
- **Вариан, 4.1-4.3** доступно о полезностях
- **JR, 1.2** очень формально о полезностях и предпочтениях
- **БЖЦ 1.5-1.6, 1А** связь предпочтений и полезностей
- **БЖЦ 1А** модель выбора

# Лекция 1, часть 1

## Зачем нужны модели

В прошлом вы уже сталкивались с разнообразными моделями, например, *уравнение Ома* $I = U/R$ описывает связь между током и напряжением, а  *уравнение Ньютона* $F = m a$ описывает связь между силой и ускорением. Возможно, вы слышали, что *кинетическая* энергия задается уравнением $$E_k = \sum_{i=1}^n \frac{m v_i^2}{2}.$$ 

Возможно, вы не отдавали себе в этом отчет, но это всего лишь модели реальности. Понять это очень легко, потому что каждый раз в уравнении присутствует латентная переменная, которую невозможно увидеть или измерить напрямую. В уравнении Ома это *ток*, а в уравнении Ньютона это *сила*. Массу и ускорение мы можем почувствовать, но кинетическая энергия существует лишь в нашем воображении.

Похожим образом, в экономике тоже есть большое количество вымышленных объектов. Как и в физике, эти уравнения связывают что то что можно измерить с чем то, что измерить нельзя. Чего стоит одна *невидимая рука рынка* Адама Смита: 

*По-видимому, какая-то невидимая рука заставляет их принимать участие в таком же распределении предметов, необходимых для жизни, какое существовало бы, если бы земля была распределена поровну между всеми населяющими её людьми. Таким образом, без всякого преднамеренного желания и вовсе того не подозревая, богатый служит общественным интересам и умножению человеческого рода..*

Первым таким вымышленным объектом в нашем курсе будет **полезность**. Мы скажем, что у каждого потребителя в голове зашита функция которая над каждым товаром, или действием, ставит определенное вещественное число.

Конечно же, никакой полезности на самом деле нет, как нет тока I, вектора силы F торчащей из пола и многих других объектов. Однако, нам **удобно так строить рассуждения**, как будто они есть.

## Что можно делать с моделями

Модели исключительно полезны. Все современное экономическое сообщество говорит между собой, так или иначе, на языке моделей. В зависимости от области применения модели могут быть: теоретические, эконометрические, бихевиористские. Вот лишь неполный список того, чего с ними можно делать

- модели можно **критиковать**. К примеру, у вашей модели есть предсказание, которое не подтверждается в данных. В таком случае вы можете пуститься на поиски новой модели, либо пуститься на поиски ошибки в коде.
- модели можно **калибровать**. Как правило, модель имеет некоторое число степеней свободы (параметров) которые можно оценить при помощи экспериментов и наблюдений.
-  модели можно **сравнивать**. Конкретно, некоторые модели являются частными случаями, или более узкими формулировками, других моделей. Если вы откалибровали узкую модель то вы всегда можете откалибровать (индуцировать) более общую модель.
- модели можно **аксиоматизировать**. Это особенно увлекательное занятие заключается в том, чтобы сформулировать минимально необходимый набор аксиом, который фиксирует желаемую структуру.
- модели можно **развивать**. Если набор аксиом уже известен, вы можете доказывать новые утверждения, опираясь на эти аксиомы.

Наконец, хорошо обоснованные и качественно откалиброванные модели можно использовать для того, чтобы производить **экономический анализ** событий прошлого, а также, строить **экономические прогнозы** относительно событий будущего.

Некоторые модели настолько хороши и убедительны, что не нуждаются в калибровке. Такие модели зачастую называются **классическими**. Наш курс, в основном, состоит в изучении именно таких моделей.

## Полезность (классика)

### Общая идея

Утилитарная, или **модель полезности** это абсолютный вакуум, в котором есть два типа сущностей: агенты и товары.

- **агентов** можно проиндексировать: $i \in 1,2,3$...
- **товары** делятся на категории: $x, y, z$...

Каждый агент может один раз выбрать комбинацию товаров, представленную точкой в Евклидовом пространстве $\mathbb{R}_{+}^n$, где плюс обозначает неотрицательные числа а $n$ это число товаров. 

Например, если товаров всего три, то $\mathbb{R}_{+}^3$ это такой (бесконечный) куб. Пусть $a, b$ это две потенциальные комбинации, тогда у точки $a$ будут три координаты $(a_x, a_y, a_z)$, а у точки $b$ три координаты $(b_x, b_y, b_z)$. 

Более того, не все комбинации из $\mathbb{R}_{+}^n$ доступны. Множество комбинаций доступных для агента $i$, как правило, обозначается заглавной буквой $X_i$.

- $X_i$ это **множество доступных альтернатив**

Вообще, в первой лекции будет ровно один агент. Далее, этот агент выбирает точку в $X_i$, которая максимизирует его полезность $U_i(x, y, z)$. 

- **полезность** $U_i$ это функция из $X_i$ в $\mathbb{R}$

Таким образом, мы может сформулировать модель потребителя как как абстрактную оптимизационную задачу:

$$ U_i(x,y,z) \to \max_{(x,y,z) \in X_i}$$

Подразумевается, что некоторые такие задачи вы уже должны уметь решать. 

P.S. Иногда буквы алфавита $x, y, z$ будут обозначать "разные точки в пространстве" а иногда "разные товары в полезности", к этому придется привыкнуть. Интерпретация букв меняется, в зависимости от контекста.

> Формально **классическая  (утилитарная) модель** (для одного агента) это пара: множество альтернатив $X \subset \mathbb{R}^n_{+}$ и полезность $U: X \to \mathbb{R}$. Никаких дополнительных аксиом не требуется.

Калибровка модели, как правило, заключается в выборе конкретной функции полезности. Предсказание модели это оптимальная комбинация товаров, в зависимости от различных предложенных $X$.

### Примеры

#### 1. Яблоки и груши

У Пети есть 100 рублей. Он может купить яблоки по цене 20 рублей за штуку либо груши по цене 50 рублей за штуку. Петя получает полезность 2 за каждое яблоко и 3 за каждую грушу, но не получает никакой полезности за оставшиеся деньги. Попробуем записать это формально:

- $X = \{(x, y) \in  \mathbb{N}^2_{+}: 20 x + 50 y \leqslant 100 \}$
- $U(x, y) = 2x + 3y$

#### 2. Учеба и вечеринки

У Кати есть 24 часа в сутки, из которых она должна как минимум 8 часов поспать, a оставшиеся часы входят в полезность вида Коб-Дуглас с одинаковыми весами, то есть, учеба и вечеринки в полезности умножаются под корнем.

- $X = \{(x, y, z) \in  \mathbb{N}^3_{+}: x + y + z \leqslant 24 \}$
- $U(x, y, z) = \mathbb{I}(x \geqslant 8)\cdot y^{1/2}z^{1/2}$

Мы поговорим о том, что такое Коб Дуглас подробнее на следующей лекции.

#### 3. Полезность от денег

У Саши есть 10,000,000 рублей, которые он может вложить в биткойн по курсу 1,000,000:1 или этериум по курсу 1,000,000:2. Саша ожидает, что через год рубль подешевеет на 10\%, биткойн подорожает на 50\% а этериум подорожает на 100\%. Опишите задачу составления оптимального инвестиционного портфеля, где полезность меряется в рублях

- $X = \{(x, y, z) \in  \mathbb{N}^3_{+}: x + 10^6 (y + 2 z) \leqslant 10^7 \}$
- $U(x, y, z) = .9 x + 1.5 y + 2 z$

## Свойства полезности

У полезностей в $\mathbb{R}^n$ часто бывает несколько (если не все) из нижеперечисленных свойств. Пусть $a, b$ это какие то комбинации товаров из множества альтернатив $X \subset \mathbb{R}^n$.

Мы начнем с двух эквивалентных определений непрерывности.

> Определение 1.1: полезность $U$ **непрерывна** в $X$, если для любого $x \in X$ множества $L_{+}(x)$ и $L_{-}(x)$ замкнуты, где
$$ L_{+}(x) = \{y \in X: U(y) \geqslant U(x)\}, \quad L_{-}(x) = \{y \in X: U(y) \leqslant U(x)\}$$

Описанные выше множества $L_{+}(x)$ (или $L_{-}(x)$) это подмножества допустимых альтернатив,  которые не хуже (или не лучше) чем сам $x$. Иногда в литературе они называются верхним и нижним Лебеговым множеством.

> Определение 1.2: полезность $U$ **непрерывна** в $X$, если для любого $\varepsilon > 0$ существует $\delta >0$ такой что для любых $x, y \in X$ верно что: $$ ||x - y|| < \delta \quad \Rightarrow \quad ||U(x) - U(y)|| < \varepsilon$$

Большую роль в истории физики и математики играют выпуклые и вогнутые функции. Например, в физике твердых тел все объекты минимизирует свою энергию. Заметим, что кинетическая энергия выпуклая, то есть, энергия с минусом вогнутая функция. Следовательно, все в физике максимизирует какую то вогнутую функцию. Естественным образом, это понятие появилось и в экономике.

> Определение 2: полезность $U$ **вогнута** если для любых $x, y \in X$: $$ \forall \alpha \in (0,1): U(\alpha x + (1-\alpha) y)) \geqslant \alpha U(x) + (1-\alpha) U(y)$$

Давать определение выпуклой полезности не имеет большого смысла с экономической точки зрения, считается, что все полезности скорее вогнуты чем выпуклы.

Зато большим смыслом обладает понятие квази-вогнутости. У него тоже будут две версии, которые почти (но не совсем) эквивалентны друг другу.

> Определение 3.1: полезность $U$ **квази-вогнутa** в $X$, если для любого $x \in X$ множество $L_{+}(x)$ выпукло, то есть, оно содержит пределы всех своих последовательностей. 

> Определение 3.2: полезность $U$ **квази-вогнута** в $X$ если для любых $x, y \in X$ их линейная комбинация не хуже чем худшая из двух:
$$ \forall \alpha \in (0,1): U(\alpha x + (1-\alpha) y)) \geqslant \min(U(x), U(y))$$

P.S. Иногда я буду делать приставку "строго", это значит что либо множество строго выпукло, либо неравенство строгое. Смотрите на контекст.

### Вогнутость против квази вогнутости

Я буду иногда называть комбинацию товаров **портфелем**, как в финансах, вместо **потребительской корзины**, для краткости.

#### Сценарий 1
Чтобы попасть на работу, вам нужно сколько то ехать сначала на автобусе, а потом на метро. В портфеле 1 у вас N билетов на автобус. В портфеле 2 у вас M билетов на метро. 

Логично предположить, что вы предпочтете усредненный портфель, в котором $\frac{M+N}{2}$ билетов на автобус и $\frac{M+N}{2}$ билетов на метро, чем получить любой из двух портфелей с вероятностью 1/2.

Это свойство означает, что ваша полезность скорее всего квази-вогнутая, но вы никак не можете проверить вогнутость без конкретной меры полезности.

#### Сценарий 2
У вас есть портфель 1 с акциями "ООО Газпром" и портфель 2 с акциями "Tesla inc.". Средневзвешенный портфель как-то разделит инвестиции между Tesla и Газпром. Будем считать, что доходность всех трех портфелей одинаковая, но они, возможно, отличаются риском. Назначим полезность равную риску с минусом.

**Вогнутость означает**, что с точки зрения риска, полезность от средне-взвешенного портфеля выше чем средняя взвешенная полезность этих двух портфелей. 

**Квази-вогнутость означает**  , что с точки зрения риска, полезность от средне-взвешенного портфеля выше чем средняя взвешенная полезность этих двух портфелей, если эти два портфеля имели одинаковый риск.

То есть, квази-вогнутость более слабое условие.

#### Связь вогнутости и квази-вогнутости

Оба термина: вогнутость и квази-вогнутость, означают либо **любовь агентов к разнообразию**, либо **комплементарность товаров**, либо **боязнь риска**, но вогнутость однозначно сильнее чем квази-вогнутость. Докажем этот простой факт:
> Утверждение 1: Из вогнутости следует квази вогнутость

Достаточно выписать цепочку неравенств:

$$ 
\begin{align*} 
(1) : & \quad U(\alpha x + (1-\alpha) y)) \geqslant \alpha U(x) + (1-\alpha) U(y) \\
(2) : & \quad \alpha U(x) + (1-\alpha) U(y) \geqslant \min (U(x), U(y))\\
(1), (2) \quad \Rightarrow & \quad U(\alpha x + (1-\alpha) y)) \geqslant \min (U(x), U(y))
\end{align*}
$$

Однако, неверно что из квази-вогнутости обязательно следует вогнутость. Можно привести огромное количество контр-примеров, например функция, напоминающая перевернутую крышу пагоды (китайский домик): $$ U(x) = -(|x|-1)^2, \quad x \in [-1,1]$$ является квази-вогнутой, но не вогнутой.

При всем этом множество $X$ у нас будет именно выпуклым, а не вогнутым.

> Определение 4: множество $X$ **выпукло** если для любых $x, y \in X$: $$ \forall \alpha \in (0,1): \alpha x + (1-\alpha) y \in X$$

Выпуклое множество содержит все свои хорды. А у квази-вогнутой функции все $L_{+}(x)$ содержат все свой хорды. Вогнутых множеств вообще не бывает.

P.S. Если множество $X$ выпукло, а функция $U$ вогнута или квази-вогнута то такая задача называется выпуклой. Выпуклые задачи имеют упрощенный алгоритм решения, я к этому вернусь ближе к концу лекции.

### Кризис классической модели

Тут начинается самое интересное. Дело в том, что для любого строго монотонного преобразования $\varphi$, две полезности: $U(x)$ и $\varphi(U(x))$ производят идентичное поведение у потребителей.  

Довольно легко генерировать примеры идентичных функций используя такие монотонные преобразования как $\varphi(z) = z + c, cz , \log z$. Все ниже перечисленные полезности эквивалентны в этом смысле:

$$
\begin{align*}
& x^2y^3,\\
& 2\log x + 3\log y,\\
& 2\log x + 3\log y + 1,\\
& 2(2\log x + 3\log y) + 1.
\end{align*}
$$

То есть, нет никакой возможности откалибровать полезность в пространстве функций. Это очень грустный вывод, от него веет какой то безвыходностью.

Хуже того, всеми любимое свойство вогнутости с легкостью нарушается при монотонной трансформации. Поэтому, оно совершенно не подходит для экономического анализа. 

Однако, не все так плохо. Квази-вогнутость сохраняется при таких трансформациях.

> Утверждение 2: Если $U(x)$ квази-вогнута, то $\varphi(U(x))$ тоже квази-вогнута для любого строго монотонного преобразования $\varphi$. 

Доказательство этого факта легко выписывается, используя любое из двух определений, если знать следующие свойства:
$$ \begin{align*}
U(x) \leqslant U(y) \quad \Leftrightarrow \quad \varphi(U(x)) \leqslant \varphi(U(y))\\
U(x) \geqslant U(y) \quad \Leftrightarrow \quad \varphi(U(x)) \geqslant \varphi(U(y))\\
\min(\varphi(U(x)), \varphi(U(y))) = \varphi(\min(U(x),U(y)))
\end{align*}$$ верное для любых функций $U$ и строго монотонных преобразований $\varphi$.

Более того, если начать с выпуклой функции и начать ее монотонно деформировать, то мы можем гарантировать квази-вогнутость (но не вогнутость).

> Утверждение 3: Если $U(x)$ вогнута, то $\varphi(U(x))$ квази-вогнута для любого строго монотонного преобразования $\varphi$. 

Доказательство этого факта тривиально следует из того, что вогнутая функция уже квази-вогнута, и Утверждения 2. Все это дает надежду на то, что должен быть способ построить модель, инвариантную к монотонным преобразованиям.

P.S. Конечно, можно сказать что вместо конкретной полезности у агента мы рассматриваем класс эквивалентности по отношению к трансформациям $\varphi$. Однако, это ту мач абстрактно.

## Предпочтения (нео-классика)

### Общая идея

Снова, в вакууме, у нас есть альтернативы и агенты. Однако, вместо полезности у каждого агента в голове зашито **бинарное отношение** $\succcurlyeq$, называемое (слабым) **предпочтением**. Это довольно сложная штука.

Если полезность $U$ действовала из $X$ в $\mathbb{R}$, то предпочтение $\succcurlyeq$ действует из $X^2$ в $\{0,1\}$. То есть, для каждой упорядоченной пары альтернатив $x, y \in X$ агент знает, (слабо )предпочитает ли он $x$ по отношению к $y$ или нет. Вернее, $x  \succcurlyeq y$ интерпретируется как "x не хуже чем y".

Формально $\succcurlyeq$ задается таблицей, например, для трех альтернатив:

$$ 
\begin{array}{c|cc}
 \succcurlyeq & x & y & z\\
\hline
x & 1 & 1 & 0 \\
y & 0 & 1 & 1\\
z & 0 & 1 & 0\\
\end{array}
$$

Для простоты, вводятся дополнительные обозначения:

$x \succcurlyeq y$ означает что $(x,y) \mapsto 1$
$x \preccurlyeq y$ означает что $(y,x) \mapsto 1$
$x \sim y$ означает что $x \succcurlyeq y$ и $x \preccurlyeq y$ 
$x \succ y$ означает что $x \succcurlyeq y$ но не $x \sim y$
$x \prec y$ означает что $x \preccurlyeq y$ но не $x \sim y$

Получаются пять интуитивных отношений сильного, слабого предпочтений и безразличия. Однако, какие попало матрицы писать не стоит.

## Рациональность

Ясно, что бинарные отношения, как они есть, это слишком абстрактно. Попробуем добавить немножко структуры.

> Определение 5: предпочтения **рациональны** если выполнены следующие три свойства:

- для любыx альтернатив $x, y \in X$, хотя бы $x \succcurlyeq y$ либо $y \succcurlyeq x$.
- для любой альтернативы $x \in X$, всегда верно что $x \sim x$
- для любыx альтернатив $x, y, z \in X$: $$ x \succcurlyeq y, y \succcurlyeq z \quad \Rightarrow \quad x \succcurlyeq z$$

Последнее свойство - самое важное и называется **транзитивностью**. Рациональность накладывают структуру на то как может заполняться матрица. Попробуйте до-заполнить следующую матрицу так, чтобы предпочтения были рациональными: 

$$ 
\begin{array}{c|cc}
 \succcurlyeq & x & y & z\\
\hline
x & * & * & * \\
y & 0 & * & 1\\
z & 0 & 1 & *\\
\end{array}
$$

Ясно, что на диагонали всегда обязаны стоять единички. Также, если где то вне диагонали стоит ноль, то на симметричной относительно диагонали позиции обязательно стоит единица.

> Формально **нео-классическая модель** (для одного агента) это пара: множество альтернатив $X \subset \mathbb{R}^n_{+}$ и предпочтения $\succcurlyeq: X^2 \to \{0,1\}$. Предпочтения должны быть рациональные.

### Непрерывность и выпуклость

Практически копипастой мы определяем непрерывность предпочтений.

> Определение 1.3: предпочтения $\succcurlyeq$ **непрерывны** в $X$, если для любого $x \in X$ множества $L_{+}(x)$ и $L_{-}(x)$ замкнуты, где
$$ L_{+}(x) = \{y \in X: U(y) \geqslant X\}, \quad L_{-}(x) = \{y \in X: U(y) \leqslant X\}$$

И совершенно аналогично мы переносим квази-вогнутость в мир предпочтений, однако, вопреки логике, термин квази-ВОГНутости полезности превращается в ВЫПУклость предпочтений.

> Определение 3.3: предпочтения $\succcurlyeq$ **выпуклы** в $X$, если для любого $x \in X$ множество $L_{+}(x)$ выпукло, то есть, оно содержит пределы всех своих последовательностей. 

Парадокс в том, что вогнутые полезности квази-вогнуты, которые, в свою очередь, ассоциированы с выпуклыми предпочтениями. А выпуклые полезности с выпуклыми предпочтениями вообще никак не связаны и даже прямо противоположны им. Это просто ужасный  выбор слов и вызывает огромную путаницу. Постарайтесь запомнить что

- хорошие множества выпуклы
- хорошие полезности (квази) вогнуты
- хорошие предпочтения выпуклы, потому что их $L_{+}$ выпуклы

### Прямая связь между полезностями и предпочтениями

Предположим, что у вас уже есть откалиброванная полезность. Можно ли что то сказать по поводу предпочтений? Если подумать, то окажется, что предпочтения полностью заданы следующим образом:

$$ U(x) \geqslant U(y) \quad \Leftrightarrow \quad  x \succcurlyeq y$$

В таком случае, мы будем говорить что $U$ **представляет** $\succcurlyeq$.

Это определение должно быть понятно именно на интуитивном уровне. Также должно быть понятно, что эти предпочтения будут рациональны, поскольку это просто свойства вещественных чисел:

- для любыx $U(x), U(y) \in \mathbb{R}$, либо $U(x) \geqslant U(y)$ либо $U(y) \leqslant U(x)$.
- для любого числа $U(x) \in \mathbb{R}$, всегда верно что $U(x) = U(x)$
- для любыx чисел $U(x), U(y), U(z) \in \mathbb{R}$: $$ U(x) \geqslant U(y), U(y) \geqslant U(z) \quad \Rightarrow \quad U(x) \geqslant U(z)$$


## Обратная связь, Теорема Дебре

Предположим, что у вас уже есть откалиброванные рациональные предпочтения. Можно ли восстановить по ним хотя бы одну непротиворечивую полезность? 

Оказывается, что в простых случаях, действительно, можно.

> Утверждение 4: Если $X$ конечно, то для любых рациональных предпочтений $\succcurlyeq$ существует полезность $U$, представляющая $\succcurlyeq$.

Когда $X$ конечное, то можно решить эту задачу алгоритмически. На $i$ ом шаге алгоритма вы ищите минимальный (с точки зрения $\succcurlyeq$) элемент, выставляете ему полезность $i$ и удаляете. На следующем шаге  находите минимальный из оставшихся, выставляете ему полезность $i+1$, снова удаляете, и.т.д. Если минимальных несколько, даете им одинаковую полезность.

> Утверждение 5: Если $X$ счетно, то для любых рациональных предпочтений $\succcurlyeq$, таких что для каждого элемента $x \in X$ есть конечное число элементов не хуже него, существует полезность $U$, представляющая $\succcurlyeq$.

Доказательство аналогично Утверждению 4, только здесь можно сразу назначить полезность $U(x)$ равную числу элементов не хуже $x$, и все.

В сложных случаях нам придется потребовать непрерывность предпочтений.  Это очень сложная Теорема, я не буду ее доказывать. Но на семинаре я попрошу, чтобы вам разобрали контр-пример предпочтений, которые не являются непрерывными, чтобы вы поняли существенность этого ограничения.

> Утверждение 6 [**Теорема Дебре**]: Если $X\subset \mathbb{R}^n$ связно и сепарабельно, то для любых рациональных и непрерывных предпочтений $\succcurlyeq$ существует непрерывная полезность $U$, представляющая $\succcurlyeq$.

Связность и сепарабельность это скучные технические свойства $X$,  которые все равно выполняются во всех моделях. Грубо говоря, $X$ не может быть "фракталом" или пористой как "губка". 

Однако, не стоит забывать, что, если предпосылки теоремы не выполнены, это еще не значит что полезности нет. Она может случайно сложиться, но это скорее исключение из правила.

### Разрешение кризиса классической модели

Напомним, что кризис утилитарного подхода заключается в не единственности полезности. Это очень болезненное свойство, сулящее постоянные проблемы, если с ним ничего не делать.

Мы продемонстрировали, что из любой полезности можно вывести рациональные предпочтения, а из любых непрерывных и рациональных предпочтений - непрерывную полезность.

Получается, что полезности и предпочтения это, по большому счету, одно и то же. Вернее, предпочтения эти и есть тот самый класс эквивалентности полезностей, который надо себе воображать.

Выбор представителя внутри класса эквивалентности - дело вкуса. Как только вы видите ту или иную полезность можно спокойно применять к ним монотонные преобразования, отключив при этом мозг. В частности, у вас может быть больше развита техника работы с полезностью $2 \log x + 3 \log y$ чем с полезностью $x^2 y^3.$ 

Более того, удачно наложив монотонное преобразование, можно случайно сделать функцию вогнутой, хотя она была изначально всего лишь квази-вогнута.

# Лекция 1, часть 2
## Начала оптимизации

Любая оптимизационная задача это две вещи
- функция, которую мы максимизируем
- область определения аргументов, по которым мы максимизируем

Рассмотрим несколько примеров, в которых хорошо видно, что двумя ключевыми свойствами задачи являются: выпуклость/вогнутость самой функции, а также ограниченность и положение области определения.

### Пример 1:
Парабола рогами вниз на отрезке от -1 до 1
$$ -x^2 \to \max_{x \in [-1,1]}$$ Достигает максимума в точке 0.

### Пример 2:
Парабола рогами вниз на отрезке от -2 до -1
$$ -x^2 \to \max_{x \in [-2,-1]}$$ Достигает максимума в точке -1.

### Пример 3:
Парабола рогами вверх на отрезке от -1 до 1
$$ x^2 \to \max_{x \in [-1,1]}$$ Достигает максимума в точкax -1 и 1.

### Пример 4:
Парабола рогами вверх на всей числовой прямой
$$ x^2 \to \max_{x \in \mathbb{R}}$$ Не достигает своего максимума, вообще.

### Пример 5:
Парабола рогами вверх на интервале от -1 до 1
$$ x^2 \to \max_{x \in \mathbb{R}}$$ Также не достигает максимума

### Существование решений

Существование решения, как правило, мы можем легко показать при помощи следующей теоремы

> Утверждение 7 [**Теорема Вейерштрасса**]: Непрерывная функция на компакте гарантированно достигает своего минимума и максимума.

Что такое непрерывная функция вы уже знаете. A **компакт** в $\mathbb{R}^n$ это просто ограниченное и замкнутое множество. В контексте одномерной оптимизации, $[a,b]$ это компакт, а $(a,b]$, $[a,b)$, $(a,b)$, $[a,\infty)$,$(a,\infty)$ это все не компакты. 

Говоря другими словами, у вас есть всего два сценария как решение оптимизационной задачи с непрерывной функцией могло бы не существовать: либо оно вообще бесконечно, либо оно конечно, но достигается в точке которая попала на границу области.

## Условия первого порядка

Для непрерывной функции на компакте, решение лежит либо на границе области, либо внутри, третьего не дано.

Если решение лежит внутри области, то обязательно выполнены условия первого порядка. Например, если функция $U(x, y, z)$ от трех переменных, и вы убедили себя что решение надо искать внутри, то
$$\text{УПП (FOC)}: \quad  \nabla U = 0$$ должны выполняться в оптимальной точке $(x^{\ast}, y^{\ast}, z^{\ast})$. Зачастую, граничных точек не так уж и много, и их можно просто перебрать руками, сравнивая значения. Затем можно выбрать наилучшую из граничных и внутренних точек, удовлетворяющих УПП.

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

```{mermaid}
graph TD
F((все выпукло?)) -- no --> G[думаем нестандартно...];
F -- yes --> D;
D[решаем УПП] --> A((она внутри?));
A -- yes --> B[это ответ!];
A -- no --> C[ищем на границе...];
```

То есть, мы набрасываемся на такую задачу, как будто решение у нее внутреннее. Затем проверяем, что мы не ошиблись. Если кандидат оказался внутри, то это и есть правильный ответ. Если же нет, то мы заново ищем вдоль границы, исходя из геометрических соображений.

## Линии уровня

Наконец, линии уровня это очень удобный инструмент для отлова и классификации кандидатов на решение оптимизационной задачи.

> Определение 6.1: **линией уровня** полезности $U$, 
проходящей через точку $x$ называется множество всех точек $y \in X$ таких что $U(y) = U(x)$.

> Определение 6.2: **кривой безразличия** предпочтений $\succcurlyeq$, проходящей через точку $x$ называется множество всех точек $y \in X$ таких что $x \sim y$.

Совершенно ясно, что в контексте представлений предпочтений полезностями и наоборот, кривая безразличия и линия уровня это одно и то же.

Рассмотрим несколько примеров

### Пример 1: Линейная полезность
Рассмотрим полезность вида: $U(x, y) = ax + by$. Тогда линия уровня ищется следующим образом: $$
\begin{gather*}
c = ax + by\\
c-ax = by\\
y = \frac{c-ax}{b}
\end{gather*}
$$ Линия уровня это прямая вида $y = \alpha x + \beta$.

### Пример 2: Гиперболическая полезность
Рассмотрим полезность вида: $U(x, y) = a \log x + \log y$. Тогда линия уровня ищется следующим образом: $$
\begin{gather*}
c =  a \log x + \log y\\
e^{c} = x^a y\\
y =\frac{e^{c}}{x^a}
\end{gather*}
$$ Линия уровня это гипербола вида $y = x^\alpha \beta$.

### Пример 3: Леонтьефская полезность
Рассмотрим полезность вида: $U(x, y) = \min(ax, by)$. Тогда линия уровня ищется следующим образом: $$
\begin{gather*}
c = \min(ax, by)\\
\frac{c}{b}= \min(\frac{a}{b}x, y), \quad \frac{c}{a}= \min(x, \frac{b}{a}y)\\
y = \frac{c}{b} \mathbb{I}(ax > c), \quad x = \frac{c}{a} \mathbb{I}(by > c)
\end{gather*}
$$ Линия уровня это конкатенация горизонтальной и вертикальной линий, соединенных вдоль $ax = by$.

### Зачем нужны линии уровня?
Очень часто, в задачах есть выпуклое ограничение типа неравенства, например, бюджетное ограничение . В таком случае, все кандидаты будут формально не внутренние. Однако, с точки зрения выпуклой оптимизации, такие точки можно интерпретировать как "внутренние", если решать методом Лагранжа. О методе Лагранжа мы поговорим на следующей лекции.

Внутреннее решение выпуклой (и гладкой) оптимизационной задачи можно охарактеризовать как точку касания линии уровня с выпуклым ограничением. 

Иногда задача вообще не является гладкой, как в случае Леонтьефских полезностей. Тогда линии уровня это самый быстрый и надежный подход к решению задачи. 

# Задачи для семинара и/или самостоятельного разбора

### Задача 0.1
Рассмотрим классическую модель с полезностью $U(\ast) = f^3(\ast)$ и множеством альтернатив $X = \{x, y, z, w\}$, таким что $$f(x) = -1, f(y) = 1, f(z) = 0, f(w) = 2.$$ Заполните матрицу предпочтения $\succcurlyeq$ ассоциированного с $U(\ast)$:
$$ 
\begin{array}{c|ccc}
 \succcurlyeq & x & y & z & w\\
\hline
x  & 1  & * & * & *\\
y  & *  & 1 & * & *\\
z  & *  & *  & 1 & *\\
w & *  & * & * & 1\\
\end{array}
$$

### Задача 0.2
Рассмотрим нео-классическую модель с предпочтениями $\succcurlyeq$ на множестве альтернатив $X = \{x, y, z, w\}$, заданными матрицей:
$$ 
\begin{array}{c|ccc}
 \succcurlyeq & x & y & z & w\\
\hline
x  & 1  & 1 & 1 & 0\\
y  & 0  & 1 & 1 & 0\\
z  & 0  & 0  & 1 & 0\\
w & 1  & 1 & 1 & 1\\
\end{array} \quad \quad \quad \quad U(*) = ?
$$

Подберите полезность которая представляет такие предпочтения.

### Задача 0.3

Рассмотрим экзотическую модель с предпочтениями $\succcurlyeq$ на $X$, которые заданы следующим образом. Для двух рациональных предпочтений $\succcurlyeq_1$ и $\succcurlyeq_2$ на том же множестве альтернатив, определим
$$ x \succcurlyeq y \quad \Leftrightarrow \quad x \succcurlyeq_1 y \quad \text{и} \quad x \succcurlyeq_2 y$$ То есть, в нашей экзотической модели, $x$ предпочитается $y$ тогда и только тогда, когда $\succcurlyeq_i$ единогласно предпочитают $x$. Докажите, что $\succcurlyeq$ рациональное предпочтение, или приведите контрпример.

### Задача 0.4

Докажите, что пересечение двух выпуклых множеств выпукло.

### Задача 0.5

Промаксимизируйте функцию $(x-a)^2$ на отрезке $[-1,1]$. Запишите ответ как функцию от $а$.

$$ 
x^{\ast}(a) = (\ldots)\cdot \mathbb{I}(a> \ldots) +  (\ldots) \cdot \mathbb{I}(a< \ldots)
$$

### Задача 0.6

Используя сначала метод линий уровня, а затем (или одновременно) метод Лагранжа, решите следующую оптимизацинную задачу:

$$ 
x y \to \max_{(x,y) \in \mathbb{R}^2_{+}} \quad s.t. \quad x^2 + q y^2 \leqslant 1
$$

Является ли эта задача выпуклой?

### Задача 0.7

Рассмотрим **лексикографические предпочтения** (такие что мы ранжируем сначала по первой координате, потом по второй, и так далее...) на $\mathbb{N}^n_{+}$. Докажите, что предпосылки Теоремы Дебре не выполняются, но полезность, тем не менее, можно построить.

Рассмотрим лексикографические предпочтения  на $\mathbb{R}^n_{+}$. Докажите, что предпосылки Теоремы Дебре не выполняются. Как вы думаете, удастся ли построить полезность? Если нет, то в чем проблема?

# Домашнее задание 1

## Первый блок задач (10 баллов)

### Задача 1.1 (1 балла)
Рассмотрим нео-классическую модель с предпочтениями $\succcurlyeq$ на множестве альтернатив $X = \{-2, -1, 1, 2\}$, заданные графом на Рис. 1 в лекции.

Заполните матрицу бинарного отношения а также подберите глобальную функцию (композиция элементарных), которая ее представляет:
$$ 
\begin{array}{c|ccc}
 \succcurlyeq & -2 & -1 & 1 & 2\\
\hline
-2  & 1  & * & * & *\\
-1  & *  & 1 & * & *\\
1  & *  & *  & 1 & *\\
2 & *  & * & * & 1\\
\end{array} \quad \quad \quad \quad U(*) = ?
$$

### Задача 1.2 (2 балла)
Рассмотрим нео-классическую модель с предпочтениями $\succcurlyeq$ на множестве альтернатив $X = \{x, y, z, w\}$, матрицей
$$ 
\begin{array}{c|ccc}
 \succcurlyeq & x & y & z & w\\
\hline
x  & *  & * & * & *\\
y  & 0  & * & * & * \\
z  & *  & 0  & * & * \\
w & 0  & 0 & 0 & * \\
\end{array}
$$

Как вы думаете, какое минимально необходимое число экспериментов надо провести, чтобы гарантированно полностью откалибровать эту модель? Аргументируйте.

Эксперимент это вопрос, который вы задаете человеку в Лаборатории Экспериментальной Экономики. Когда вы калибруете нео-классическую модель, вы предполагаете, что все необходимые аксиомы выполнены.

### Задача 1.3 (2 балла)

Рассмотрим экзотическую модель с предпочтениями $\succcurlyeq$ на $X$, которые заданы следующим образом. Для двух рациональных предпочтений $\succcurlyeq_1$ и $\succcurlyeq_2$ на том же множестве альтернатив, определим
$$ x \succcurlyeq y \quad \Leftrightarrow \quad x \succ_1 y \quad \text{или} \quad (x \sim_1 y \quad \text{и} \quad x \succcurlyeq_2 y)$$ То есть, в нашей экзотической модели, $x$ предпочитается $y$ тогда и только тогда, когда либо $\succcurlyeq_1$ предпочитает $x$, либо $\succcurlyeq_1$ безразличен но тогда $\succcurlyeq_2$ предпочитает $x$. Докажите, что $\succcurlyeq$ рациональное предпочтение, или приведите контрпример.

### Задача 1.4 (5 балла)

Рассмотрим новую модель поведения потребителя, отличную от предпочтений и полезностей. Модель состоит из пространства альтернатив $X$ и отображения $C$ которое ставит любому подмножеству $Y \subset X$ уже его подмножество $Z \subset Y \subset X$, обязательно непустое. Будем называть $Y$ - **меню** a $Z$ - **выбор**.

То есть, мы предлагаем агенту меню с товарами, а он вычеркивает из него часть (или, возможно, ничего не вычеркивает, но главное чтобы он не вычеркнул вообще все) и возвращает меню со словами "это мой выбор".

> **Слабая Аксиома Выбора** (WARP) говорит, что для двух портфелей $x, y \in X$ невозможно, чтобы в одном меню $Y'$: $x$ был выбран в присутствие $y$, а в другом меню $Y''$: $y$ был выбран в присутствие $x$, но $x$ выбран не был. Подразумевается, что $x, y \in Y'$ и $x, y \in Y''$.

Придумайте как вывести модель выбора из модели предпочтений. Докажите, что для рациональных предпочтений, ассоциированный с ними выбор всегда удовлетворяет WARP. 

> **Обобщенная Аксиома Выбора** (GARP) говорит, что для последовательности  портфелей $x_1, x_2, \ldots x_n \in X$ невозможно, чтобы в одном меню: $x_1$ был выбран в присутствие $x_2$, в другом меню $x_2$ был выбран в присутствие $x_3$, и так далее... до $x_n$. А в еще одном меню $x_n$ был выбран в присутствие $x_1$, но $x_1$ выбран не был. 

Придумайте как вывести модель предпочтений из модели выбора. Докажите, что в модели выбора, удовлетворяющей GARP, ассоциированные предпочтения обязательно рациональны.

## Второй блок задач (10 баллов)

### Задача 2.1 (1 балл)

Дозаполните определения выпуклого множества, полезности и предпочтения, постарайтесь не запутаться:

> множество $X$ выпукло если для любых $x,y \in X$: $$ \forall \alpha \in (0,1): \quad \alpha x + \ldots$$

> полезность $U$ выпуклa если для любых $x,y \in X$: $$ \forall \alpha \in (0,1): \ldots$$

> предпочтения $\succcurlyeq$ выпуклы если для любых $z \in X$ и $x, y \in L_{+}(x)$: $$ \forall \alpha \in (0,1): \quad \alpha x + \ldots$$

### Задача 2.2 (1 балл)

Докажите, что объединение двух выпуклых множеств выпукло, либо приведите контрпример.

### Задача 2.3 (2 баллa)

Промаксимизируйте функцию $-(x-1)^2$ на отрезке $[-b,b]$. Запишите ответ как функцию от $b>0$.

$$ 
x^{\ast}(b) = (\ldots)\cdot \mathbb{I}(b> \ldots) +  (\ldots) \cdot \mathbb{I}(b< \ldots)
$$

### Задача 2.4 (2 балл)

Используя сначала метод линий уровня, а затем метод Лагранжа (если сможете), решите следующую оптимизацинную задачу:

$$ 
\min(x, y) \to \max_{(x,y) \in \mathbb{R}^2_{+}} \quad s.t. \quad x + q y \leqslant 1
$$

Является ли эта задача выпуклой?

### Задача 2.5 (4 балла)

Рассмотрим полезность вида $U(x, y) = x^{\alpha} y^{\beta}$ в пространстве  альтернатив $\mathbb{R}^2_{+}$, то есть, $x, y>0$. 
- Используя *Гессиан*, найдите все $\alpha, \beta >0$ такие что полезность вогнутая. 
- Используя *Окаймленный Гессиан*, найдите все  $\alpha, \beta>0$ при которых полезность квази-вогнутая. 
- Наконец, найдите все  $\alpha, \beta>0$ при которых полезность является монотонным преобразованием некоторой вогнутой функции.

Пользуйтесь строгими версиями вогнутости или критерия, по вкусу.