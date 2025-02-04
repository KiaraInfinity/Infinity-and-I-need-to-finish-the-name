# Probability Theory

## Seminar 2

$X, X \sim N(0, 1)$
- $\varphi(x) = \frac 1 {\sqrt {2\pi}}e^{-\frac {x^2}{2}};\ x \in \mathbb R;$
- $\Phi(x)= \int \limits_{-\infty}^x \varphi(t)dt$

**Напоминание:** $\Phi$ и $\varphi$ - специальное обозначение функций распределения и плотности соответственно для *нормального распределения*

### Хи-квадрат распределение с $n$ степенью свободы

- **Def.** $Y = X^2 \sim \chi^2 (1)$ - *хи-квадрат распределение с первой степенью свободы*

$F_Y(Y) = \mathbb P(X^2 \leq y; y > 0) = \mathbb P\big(-\sqrt y \leq X \leq \sqrt y\big) =$$
$$= \Phi(\sqrt y) - \big(1 - \Phi (\sqrt y)\big) = 2\Phi(\sqrt y) - 1$

#### Гамма-распределение:

$X \sim g_p(x)$ - гамма-распределение с параметром $p$, если:

$$\begin{equation*}f_x (x) = \begin{cases}\frac 1 {\Gamma (p)} x^{p - 1} e^{-x};\ x \geq 0\\ 0; x < 0 \end{cases}\end{equation*}$$

### Гамма-функция Эйлера и её свойства:

***Обозначение:*** $\Gamma(p)$

$$\Gamma(p) = \int_0^{\infty} x^{p - 1}e^{-x}dx$$

- $\Gamma(1) = 1$
- $\Gamma(\frac 1 2) = \sqrt \pi$. Док-во: $\Gamma(\frac 1 2) = \int \limits_0^{\infty} x^{-\frac 1 2}e^{-x}dx = ?$ Замена:

$$x = \frac{y^2}2 \iff dx = ydy \implies \int_0^{\infty} \frac{\sqrt 2} y e^{-\frac{y^2} 2} ydy =$$
$$= \frac {\sqrt 2} {\sqrt {2\pi}} \sqrt {2\pi} \underbrace{\int \limits_0^{\infty} e^{-\frac{y^2} 2}dy}_{\text{плотность эксп. р-я}} = \sqrt \pi \cdot 1 = \sqrt \pi$$

- $\Gamma(n) = (n - 1)!$

Про сумму:

$$Z = X^2 + Y^2;\ Z \in \chi^2(2);\ X, Y \in N(0, 1); X, Y - \text{нез.}$$

$\implies$ Тогда $Z \sim \chi^2(2),$ где $2$ - количество степеней свободы

Функция плотности:

$$\begin{equation*}f_Z (z) = \begin{cases}\frac {e^ {-\frac z 2}} 2;\ z \geq 0\\ 0; z < 0 \end{cases}\end{equation*} \sim\frac 1 2g_{\frac 2 2}\bigg(\frac z 2\bigg)$$
$$f_Z(z) = \int \limits_0^{\infty}f_{X^2} \cdot f_{Y^2}(z - x)dx = \frac 1 {\sqrt {2 \pi}}\int \limits_0^{\infty}e^{-\frac x 2}\cdot x^{-\frac 1 2}\cdot$$
$$\cdot f_Y(z - x)dx = \frac 1 {\sqrt {2 \pi}}\int \limits_0^ze^{-\frac x 2}\cdot x^{-\frac 1 2}\cdot \frac 1 {\sqrt {2\pi}}e^{-\frac{(z - x)} 2}(z - x)^{-\frac 1 2}dx =$$
$$= \frac 1 {\sqrt {2\pi}} e^{-\frac z 2}\int \limits_0^zx^{-\frac 1 2}(z - x)^{-\frac 1 2}dx$$
Замена: $x = yz; dx = zdy$
$$\frac 1 {\sqrt {2\pi}}e^{-\frac z 2}\int \limits_0^1(yz)^{-\frac 1 2}(z - yz)^{-\frac 1 2} \cdot zdy = \frac 1 {\sqrt{2\pi}}e^{-\frac z 2}\underbrace{\int \limits_0^1 y^{-\frac 1 2}(1 - y)^{-\frac 1 2}dy}_{K}$$

Из основного свойства функции плотности:

$$1 = \frac K {\pi} \cdot \underbrace{\frac 1 2 \int \limits_0^{\infty}e^{-\frac z 2}dz}_{= 1} = \frac K \pi \implies K = \pi$$

Свойство суммы нормальных распределений:

$$X = X_1^2 + \ ...\ + X_n^2;\ X_i \sim N(0, 1), X_i - \text{нез.}$$

Тогда $X \sim \chi^2(n);$

$$f_x(x) = \frac 1 2 \cdot g_{\frac n 2}\big(\frac x 2\big) = \begin{equation*}\begin{cases}\frac 1 2 \cdot \frac 1 {\Gamma(\frac n 2)} \cdot \big(\frac x 2\big)^{\frac n 2 - 1} e^{-\frac x 2};\ x \geq 0\\ 0; x < 0 \end{cases}\end{equation*}$$

- **Утв.** $X \sim N(0, 1) \implies \mathbb E[X^r] = \int \limits_{-\infty}^{\infty}x^r \cdot \frac 1 {\sqrt {2\pi}}e^{-\frac {x^2}2}dx$
- Если $r$ - нечётное, т. е., $r = 2k - 1; k = 1, 2... \implies \mathbb E [X^{2k - 1}] = 0$ - подынтегральная нечётная функция
- Если $r$ - чётное, т. е., $r = 2k$
  $$\implies \mathbb E[X^{2k}] = \frac 2 {\sqrt{2\pi}}\int \limits_0^{\infty}x^{2k}e^{-\frac {x^2} 2}dx = ?$$
  Замена: $y = \frac {x^2} 2; dy = xdx$
  
  $$\frac {\sqrt 2} {\sqrt{\pi}}\int \limits_0^{\infty}(2y)^k e^{-y} \cdot \frac 1 {\sqrt{2y}} dy = \frac{2^k}{\sqrt{\pi}}\int \limits_0^{\infty}y^{k - \frac 1 2}e^{-y}dy = \frac {2^k}{\sqrt \pi} \cdot \Gamma(k + \frac 1 2)$$

$k - \frac 1 2 = k + \frac 1 2 - 1$

- $k = 1:$
  $$\mathbb E[X^2] = \frac 2 {\sqrt \pi}\Gamma(\frac 3 2) = \frac 2 {\sqrt \pi}\cdot \frac 1 2 \Gamma \bigg(\frac 1 2\bigg) = 1$$
- $k = 2:$
  $$\mathbb E[X^4] = \frac {2^2} {\sqrt \pi}\Gamma\bigg(\frac 5 2\bigg) = \frac {2^2} {\sqrt \pi}\cdot \frac 3 2 \cdot \Gamma \bigg(\frac 3 2\bigg) = \frac {2^2}{\sqrt \pi} \cdot \frac 3 2 \cdot \frac 1 2\cdot \Gamma\bigg(\frac 1 2\bigg) = 3$$
- $k = 3:$

- $$\mathbb E [X^{2k}] = 2^k\bigg(k - \frac 1 2\bigg) \cdot \bigg(k - \frac 3 2 \bigg)\ ... \ \cdot \frac 1 2$$

### ЦПТ (центральная предельная теорема):

$X_1, ... X_n$ - последоветельность *независимых одинаково распределённых* случайных величин; $0 < \mathbb D[X_i] < \infty;\ i \leq N\ \forall\ \mathit B \subset \mathbb R$

$\implies$ Тогда:

$$\lim_{n \rightarrow \infty} \mathbb P\bigg(\frac {S_n - \mathbb E [S_n]}{\sqrt{\mathbb D[S_n]}}\bigg) \in \mathit B = \int \limits_\mathit B \frac 1 {\sqrt{2\pi}}e^{-\frac {t^2} 2}dt; S_n = \sum_{i = 1}^n X_i$$

### Problem №8

- $n = 100$
- $X_i$ - доходы; $Y_i$ - расходы
- $X_i \sim U[100.000; 200.000]; Y_i \sim U[50.000; 150.000]$

#### Subproblem (a)

$$\mathbb P\bigg(\sum_{i = 1}^n X_i > 45 \cdot 10^6\bigg) = ?$$
С помощью *нер-ва Маркова*:

$$\mathbb P(\xi \geq \varepsilon) \leq \frac{\mathbb E[\xi]}{\varepsilon};\ \xi \geq 0 - \text{СВ}$$

Найдём матожиданиe и дисперсию $X_i$: $\mathbb E[X_i] = 150 000;\ \mathbb D[X_i] = \frac {10^{10}}{12}$

$$\mathbb P\bigg(\sum_{i = 1}^n X_i > 45 \cdot 10^6\bigg) \leq \frac{\mathbb E(\sum_{i = 1}^n X)}{45 \cdot 10^6} = \frac{15 \cdot 10^6}{45 \cdot 10^6} = \frac 1 3$$

#### Subproblem (b)

$$\mathbb P\bigg(\sum_{i = 1}^n X_i  - \mathbb E\bigg(\sum_{i = 1}^n X_i\bigg)< 5 \cdot 10^6 \bigg) =\ ?$$

C помощью неравенства Чебышёва:

$$\forall \xi > 0:\ \mathbb P\big(\big|\xi  - \mathbb E[\xi]\big| \geq \varepsilon \big) \leq \frac {\mathbb D[X]}{\varepsilon^2}$$

$$\mathbb P\bigg(\sum_{i = 1}^n X_i  - \mathbb E\bigg(\sum_{i = 1}^n X_i\bigg)< 5 \cdot 10^6 \bigg) =$$
$$1 - \mathbb P (\sum_{i = 1}^n X_i  - \mathbb E\bigg(\sum_{i = 1}^n X_i\bigg) \geq 5 \cdot 10^6 \bigg) \geq $$
$$\geq 1 - \frac {10^{12}}{12 \cdot 12 \cdot 25 \cdot 10^{12}} \geq 1 - \frac 1 {300} \geq \frac {299}{300}$$

#### Subproblem (c)

С помощью *ЦПТ:*

$$\mathbb P\bigg(\sum_{i = 1}^n X_i > 18 \cdot 10^6\bigg) = ?$$

$$\lim_{n \rightarrow \infty} \mathbb P\bigg(\frac {S_n - \mathbb E [S_n]}{\sqrt{\mathbb D[S_n]}} > \frac{18 \cdot 10^6 - 10^2 \cdot 15 \cdot 10^4}{\sqrt{10^2 \cdot \frac{10^10}{12}}}\bigg) =$$
$$= \mathbb P\bigg(\frac{S_n - \mathbb ES_n}{\sqrt{\mathbb D[S_n]}} > 6\sqrt 3\bigg)$$

$$\mathbb P\bigg(\sum_{i = 1}^n X_i > 18 \cdot 10^6\bigg) \simeq 0$$
- из *правила трёх сигм*: $\mathbb P\big(\xi 6 \sqrt 3\big) = 1 - \Phi(6\sqrt 3) \simeq 0$

#### Subproblem (d)

$$\mathbb P\bigg(\sum_{i = 1}^n X_i  - \sum_{i = 1}^n X_i\bigg) > 7 \cdot 10^6 \bigg) =\ ?$$

$$S_n = \sum_{i = 1}^n(X_i - Y_i); \mathbb E[S_n] = n \cdot 50 000 = 5 \cdot 10^6;$$
$$\mathbb DS_n = \bigg(\frac{10^{10}}{12} + \frac {10^{10}}{12}\bigg) \cdot 100 = \frac{10^{12}} 6 = {10^{12}} 6$$

$$\mathbb P \bigg(\frac{S_n - \mathbb E[S_n]}{\sqrt{\mathbb D[S_n]}} > \frac{(7 \cdot 10^6 - 5 \cdot 10^6)\sqrt 6}{10^6}\bigg) = \mathbb P(\xi > 2\sqrt 6) \simeq 0$$

- тоже из правила трёх сигм

### Problem 9.

- Первый лучник:
  $$\begin{equation*}X_i = \begin{cases}1;\ p = 0.5\\ 0; q = 0.5 \end{cases}\end{equation*}$$
- Второй:
  $$\begin{equation*}Y_i = \begin{cases}1;\ p = 0.4\\ 0; q = 0.6 \end{cases}\end{equation*}$$
- $n = 50$

#### Subproblem (a)

$$\mathbb P\bigg[\sum_{i = 1}^{50}X_i \geq 30\bigg] = ?$$

Так как обе случайные величины имеют распределение *Бернулли*, матожидание суммы каждой из них равно $np$ - то есть, $\mathbb E\big[\sum_{i = 1}^{50}X_i\big] = 0.5 \cdot 50 = 25$

$\mathbb D[\sum_{i = 1}^{50}X_i\big] = npq = 25 \cdot 0.5 = \frac {25} 2$. Тогда:

$$\mathbb P\bigg[\sum_{i = 1}^{50}X_i \geq 30\bigg] = \mathbb P\bigg[\sum_{i = 1}^{50}X_i \geq 30\bigg]$$
$$\mathbb P\bigg(\sum_{i = 1}^{50} X_i \geq 30 \bigg) = \mathbb P\bigg(\frac{\sum_{i = 1}^{50} X_i - \mathbb E[\sum_{i = 1}^{50} X_i]}{\sqrt{\mathbb D[\sum_{i = 1}^{50} X_i]}} \geq \frac{30 - 25}{\frac 5 {\sqrt 2}}\bigg) =$$
$= 1 - \Phi(\sqrt 2) = 1 - 0.92 = 0.08$ - значение функции распределения взяли примерное

#### Subproblem (a)

$$\mathbb P\bigg[\sum_{i = 1}^{50}X_i \geq 30\bigg] = ?$$

Так как обе случайные величины имеют распределение *Бернулли*, матожидание суммы каждой из них равно $np$ - то есть, $\mathbb E\big[\sum_{i = 1}^{50}X_i\big] = 0.5 \cdot 50 = 25$

$\mathbb D[\sum_{i = 1}^{50}X_i\big] = npq = 25 \cdot 0.5 = \frac {25} 2$. Тогда:

$$\mathbb P\bigg[\sum_{i = 1}^{50}X_i \geq 30\bigg] = \mathbb P\bigg[\sum_{i = 1}^{50}X_i \geq 30\bigg]$$
$$\mathbb P\bigg(\sum_{i = 1}^{50} X_i \geq 30 \bigg) = \mathbb P\bigg(\frac{\sum_{i = 1}^{50} X_i - \mathbb E[\sum_{i = 1}^{50} X_i]}{\sqrt{\mathbb D[\sum_{i = 1}^{50} X_i]}} \geq \frac{30 - 25}{\frac 5 {\sqrt 2}}\bigg) =$$
$= 1 - \Phi(\sqrt 2) = 1 - 0.92 = 0.08$ - значение функции распределения взяли примерное

## Seminar 3

### Полезные свойства:

1. Величина с распределением Пуассона устойчива относительно сложения (свёртка сохраняет распределение); условие - независимость слагаемых-случайных величин
2. Центральная предельная теорема:
   $$\lim_{n \rightarrow \infty}\frac{\sum_{i = 1}^n X_i - \mathbb E X_i}{\sqrt{\mathbb D[\sum_{i = 1}^n]}} = \Phi(X)$$
3. 

### Problem 1

Найти предел по вероятности (из прошлого листа):

$$\lim_{n \rightarrow \infty} {\mathbb P}(X_n - Y_n \leq \sqrt {2n})$$

$-$ при том, что $X_n$ и $Y_n$ независимы; $X_n, Y_n \sim \text{Pois}(n)$

$$X_n = \sum_{i = 1}^n;\ X_i \sim \text{Pois}(1); Y_n = \sum_{i = 1}^n;\ X_i \sim \text{Pois}(1)$$ 

1. Во-первых, знаем по правилу свёртки - случайная величина с *распределением Пуассона устойчива относительно сложения*
2. Теперь ищем саму вероятность, свернув две величины в одну сумму (а точнее - в разность):
   $${\mathbb P}\bigg\{\underbrace{\sum_{i = 1}^n(X_n - Y_n)}_{= S_n} \leq \sqrt {2n}\bigg\} = \mathbb P\bigg\{\frac{S_n - 0}{\sqrt{2n}} \leq 1\bigg\} \overbrace{\simeq}^{ЦПТ} \Phi(1)$$

   - При этом:
   $$\mathbb E \big[S_n\big] = 0; \mathbb D \big[S_n\big] = (\sqrt{2n})^2 = 2n$$

### Problem 4

$$X_i = \begin{equation*}\underbrace{X_i}_{i = 1, ... n} = \begin{cases}1;\ p = 0,2 \\ 0;\ 1 - p = 0,8\end{cases}\end{equation*}$$

События независимы; $\mathbb E X_i = p = 0,2;\ \mathbb D X_i = pq = 0,16$

$X = \sum_{i = 1}^n X_i \sim B_i (n, p = 0,2)$ - распределение Бернулли
$p = \frac{\sum_{i = 1}^n X_i}{n}$ - это *эмпирическая доля*

$$\mathbb P(|p - p| \leq 0.01) = 0.01; \mathbb P(|p - p| \geq 0.01) = 0.09$$

#### Subproblem 1:

Для таких условий найти в эмпирической доле $n$

1. Из неравенстава Чебышева знаем:
   $$\mathbb P(|p - p| \leq 0.01) < \frac{\mathbb D (p)}{(0,01)^2}$$
2. Ищем $\mathbb D(p):$ она равна $\frac{\mathbb D(X_i)}{n^2}$ (раскладывать дисперсиию *суммы* в дисперсию *сумм* можно потому, что события *независимые*; $n$ выносится за скобки с квадратом как константа)
   Получаем (умножаем $n$ дисперсий на $n$):
   $$\frac{0.16}{n^2} \cdot n = \frac{0.16}{n}$$
3. $$\mathbb P(|p - p| \leq 0.01) \leq 0.1 \implies n = 16 \cdot 10^3$$
4. Можно уточнить - из ЗБЧ:
   $$\mathbb P\bigg(\frac{\sum_{i = 1}^n X_i - n\mathbb E X_1}{\sqrt{n\mathbb D[X_1]}} \leq x \bigg) =  \mathbb P\bigg(\frac{\frac{\sum_{i = 1}^n X_i} n - \mathbb E X_1}{\sqrt{\frac{\mathbb D[X_1]} n}} \leq x\bigg)$$

   Тогда:

   $$\mathbb P(|p - 0.2| \leq 0.01) = $$
5. 


$$\mathbb P(|p - p| \leq 0.01) = 0.9; \mathbb P(|p - p| \geq 0.01) = 0.1$$