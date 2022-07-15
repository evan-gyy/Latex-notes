# Latex公式入门

:book:Latex数学公式入门笔记

- :video_camera:参考视频：[latex中文教程](https://www.bilibili.com/video/BV15x411j7k6?share_source=copy_web)，[LaTex公式教程](https://www.bilibili.com/video/BV1no4y1U7At?share_source=copy_web)
- :pencil:在线编辑器：[Online LaTeX Equation Editor](https://latex.codecogs.com/eqneditor/editor.php)

# 1 行内公式

## 1.1 单美元符号

:heavy_dollar_sign:交换律是 $a+b=b+a$，如 $1+2=2+1=3$。

```latex
$a+b=b+a$
```

# 2 上下标

## 2.1 上标

> **注意：**指数部分如大于一位需要用**`{}`**括起来

- $3x^{20}-x+2=0$

- $3x^{3x^{20} - x + 2} - x + 2 = 0$

  ```latex
  3x^{20}-x+2=0
  3x^{3x^{20} - x + 2} - x + 2 = 0
  ```

## 2.2 下标

> 用下划线**`_`**连接下标，如果数字大于一位则需要使用**`{}`**

**普通下标：**

- $a_0, a_1, a_2$

- $a_0, a_1, a_2, ..., a_{100}$

  ```latex
  a_0, a_1, a_2, ..., a_{100}
  ```

**斜体与直立体：**

- $x_i$：$i$表示1,2,...,n，为变量

- $x_{\rm i}$：$\rm i$表示“输入”，为普通文本

- 可以用`\text`或`\rm`实现直立体

  ```latex
  x_i, x_{\text i}, x_{\rm i}
  ```


# 3 希腊字母

## 3.1 直接使用

> 希腊字母的大小写由==首字母==的大小写区分

- $\alpha \ \beta \ \gamma \ \epsilon \ \pi \ \omega$

- $\Gamma \ \Delta \ \Theta \ \Pi \ \Omega$

  ```latex
  \alpha \ \beta \ \gamma \ \epsilon \ \pi \ \omega
  \Gamma \ \Delta \ \Theta \ \Pi \ \Omega
  ```

## 3.2 在公式中使用

- $\alpha^3 + \beta^2 + \gamma = 0$

  ```latex
  \alpha^3 + \beta^2 + \gamma = 0
  ```

# 4 数学函数

## 4.1 基本函数

- $\log\ \ln$

- $\sin\ \cos\ \arcsin\ \arccos$

  ```latex
  \log\ \ln
  \sin\ \cos\ \arcsin\ \arccos
  ```

## 4.2 组合

- $\sin^2 x + \cos^2 x = 1$

- $y=\arccos x$

- $y= \log_2 x$

- $y = \sin^{-1} x$

  ```latex
  \sin^2 x + \cos^2 x = 1
  y = \arccos x
  y = \log_2 x
  y = \sin^{-1} x
  ```

## 4.3 根号

- $\sqrt{x^2 + y^2}$

- $\sqrt{2 + \sqrt{2}}$

- $\sqrt[3]{xyz}$

  ```latex
  \sqrt{x^2 + y^2}
  \sqrt{2 + \sqrt{2}}
  \sqrt[3]{xyz}
  ```

# 5 分式

:star2:分式基本形式：**`\frac + {} + {}`**

> :thinking:如果分式太小，可以加上`\displaystyle`前缀，或使用`\dfrac`放大分式

- $\displaystyle\frac{x}{x^2 + x + 1}$

- $\displaystyle\frac{\sqrt{x-1}}{\sqrt{x+1}}$

- $\dfrac{1}{1+\dfrac{1}{x}}$

  ```latex
  \dfrac{1}{1+\dfrac{1}{x}}
  ```

- $\displaystyle\sqrt{\dfrac{x}{x^2 + x + 1}}$

  ```latex
  \displaystyle \sqrt{\frac{x}{x^2 + x + 1}}
  ```

# 6 行间公式

## 6.1 双美元符号

交换律是
$$
a + b = b + a
$$

，例如：
$$
1 + 2 = 2 + 1 = 3
$$

```latex
$$
a + b = b + a
1 + 2 = 2 + 1 = 3
$$
```

## 6.2 公式自动编号

> #### :star2:**Tips**
>
> 1. 打开自动编号：`文件 > 偏好设置 > Markdown > 公式自动编号`
> 2. 为公式添加标签：`\label{123}`
> 3. 引用公式：`\eqref{123}`

交换律见式$\eqref{com}$：

$$
a+b = b+a \label{com}
$$

```latex
% 为公式添加标签
a+b = b+a \label{com}
% 行内引用标签
$\eqref{com}$
```

# 7 矩阵

## 7.1 一般形式

- 使用`&`分割列
- 使用`\\`分割行

```latex
% 矩阵一般形式
\begin{matrix}
	0 & 1 \\
	1 & 0
\end{matrix}
```

效果如下式$\eqref{matrix_1}$：
$$
\begin{matrix}
0 & -1 \\
1 & 0
\end{matrix} \label{matrix_1}
$$

## 7.2 矩阵元素

### 7.2.1 定界符

1. 小括号

```latex
% 小括号：pmatrix
\begin{pmatrix}
	0 & 1 \\
	1 & 0
\end{pmatrix}
```

效果如下式$\eqref{matrix_2}$：
$$
\begin{pmatrix}
0 & -1 \\
1 & 0
\end{pmatrix} \label{matrix_2}
$$

2. 其他

> 注：如需单行显示多个矩阵，可以在结尾加上`\qquad`

- 中括号：`bmatrix`
- 大括号：`Bmatrix`
- 单竖线：`vmatrix`
- 双竖线：`Vmatrix`

效果如下式$\eqref{matrix_row}$：
$$
\begin{bmatrix}
0 & -1 \\
1 & 0
\end{bmatrix} \qquad

\begin{Bmatrix}
0 & -1 \\
1 & 0
\end{Bmatrix} \qquad

\begin{vmatrix}
0 & -1 \\
1 & 0
\end{vmatrix} \qquad

\begin{Vmatrix}
0 & -1 \\
1 & 0
\end{Vmatrix} \qquad \label{matrix_row}
$$

```latex
% 中括号
\begin{bmatrix}
	0 & -1 \\
	1 & 0
\end{bmatrix} \qquad
% 大括号
\begin{Bmatrix}
	0 & -1 \\
	1 & 0
\end{Bmatrix} \qquad
% 单竖线
\begin{vmatrix}
	0 & -1 \\
	1 & 0
\end{vmatrix} \qquad
% 双竖线
\begin{Vmatrix}
	0 & -1 \\
	1 & 0
\end{Vmatrix} \qquad \label{matrix_row}
```

### 7.2.2 上下标

$$
A = \begin{pmatrix}
		a_{11}^2 & a_{12}^2 & a_{13}^2 \\
		0 & a_{22}^2 & a_{23}^2 \\
		0 & 0 & a_{33}^2
	\end{pmatrix}
$$

```latex
A = \begin{pmatrix}
		a_{11}^2 & a_{12}^2 & a_{13}^2 \\
		0 & a_{22}^2 & a_{23}^2 \\
		0 & 0 & a_{33}^2
	\end{pmatrix}
```

### 7.2.3 省略号

常用省略号：

- 横向省略号`\dots`：$\dots$ 
  - 居中`\cdots`：$\cdots$
- 纵向省略号`\vdots`：$\vdots$
- 斜向省略号`\ddots`：$\ddots$

效果如下式$\eqref{matrix_dots}$：
$$
A = \begin{bmatrix}
		a_{11} & \dots & a_{1n} \\
		& \ddots & \vdots \\
		0 & & a_{nn}
	\end{bmatrix}_{n \times n} \label{matrix_dots}
$$

> 矩阵右下角标号可用`_{a \times b}`实现

```latex
A = \begin{bmatrix}
		a_{11} & \dots & a_{1n} \\
		& \ddots & \vdots \\
		0 & & a_{nn}
	\end{bmatrix}_{n \times n}
```

> :star2:**Tips：如何自定义反对角省略号**
>
> ```latex
> % 定义\adots命令
> \newcommand\adots{
>     \mathinner{
>         \kern1mu\raise1pt{.}
>         \kern2mu\raise4pt{.}
>         \kern2mu\raise7pt{\Rule{0pt}{7pt}{0pt}.}
>         \kern1mu
>  	}
>  }
> ```

## 7.3 分块矩阵

$$
B = \begin{pmatrix}
		\begin{matrix} 1&0\\0&1 \end{matrix} & {\Large 0} \\
		{\Large 0} & \begin{matrix} 1&0\\0&-1 \end{matrix}
	\end{pmatrix}
$$

```latex
B = \begin{pmatrix}
		\begin{matrix} 1&0\\0&1 \end{matrix} & {\Large 0} \\
		{\Large 0} & \begin{matrix} 1&0\\0&-1 \end{matrix}
	\end{pmatrix}
```

## 7.4 三角矩阵

$$
\begin{pmatrix}
	a_{11} & a_{12} & \cdots & a_{1n} \\
	& a_{22} & \cdots & a_{2n} \\
	&		 & \ddots & \vdots \\
	&		 &		  & a_{nn}
\end{pmatrix}
$$

```latex
\begin{pmatrix}
	a_{11} & a_{12} & \cdots & a_{1n} \\
	& a_{22} & \cdots & a_{2n} \\
	&		 & \ddots & \vdots \\
	&		 &		  & a_{nn}
\end{pmatrix}
```

## 7.5 行内小矩阵

> 行内大括号：`\left(` + `\right)`

- 复数$z = (x, y)$也可用矩阵$\left( \begin{smallmatrix} x&-y \\ y&x \end{smallmatrix} \right)$来表示。

```latex
\left( \begin{smallmatrix} x&-y \\ y&x \end{smallmatrix} \right)
```

## 7.6 array环境

1. 一般形式：

$$
\begin{array}{r|r}
	\frac{1}{2} & 0 \\
	\hline
	0 & -\frac a{bc}
\end{array}
$$

```latex
% array环境（分组）
\begin{array}{r|r}
	\frac{1}{2} & 0 \\
	\hline
	0 & -\frac a{bc}
\end{array}
```

2. 用array环境构造复杂矩阵：

$$
\newcommand\adots{
    \mathinner{
        \kern1mu\raise1pt{.}
        \kern2mu\raise4pt{.}
        \kern2mu\raise7pt{\Rule{0pt}{7pt}{0pt}.}
        \kern1mu
 	}
 }

\begin{array}{c@{\hspace{-5pt}}l}
	% 矩阵部分
	\left(
		\begin{array}{ccc|ccc}
			a & \cdots & a & b  & \cdots & b \\
			  & \ddots & \vdots & \vdots & \adots \\
			  &		   & a & b \\ \hline
			  &		   &   & c  & \cdots & c \\
			  &		   &   & \vdots & & \vdots \\
			  &		   &   & c & \cdots & c \\
		\end{array}
	\right)
	% 矩阵右侧部分
	\begin{array}{l}
		% \left.仅表示与\right\}配对
		\left. \rule{0mm}{7mm}\right\}p\\
		\\
		\left. \rule{0mm}{7mm}\right\}q
	\end{array}
	\\[-5pt]
	% 矩阵下方部分
	\begin{array}{cc}
		\underbrace{\rule{17mm}{0mm}}_m &
		\underbrace{\rule{17mm}{0mm}}_m
	\end{array}
\end{array}
$$

```latex
\begin{array}{c@{\hspace{-5pt}}l}
	% 矩阵部分(反对角省略号\adots的定义见7.2.3)
	\left(
		\begin{array}{ccc|ccc}
			a & \cdots & a & b  & \cdots & b \\
			  & \ddots & \vdots & \vdots & \adots \\
			  &		   & a & b \\ \hline
			  &		   &   & c  & \cdots & c \\
			  &		   &   & \vdots & & \vdots \\
			  &		   &   & c & \cdots & c \\
		\end{array}
	\right)
	% 矩阵右侧部分
	\begin{array}{l}
		% \left.仅表示与\right\}配对
		\left. \rule{0mm}{7mm}\right\}p\\
		\\
		\left. \rule{0mm}{7mm}\right\}q
	\end{array}
	\\[-5pt]
	% 矩阵下方部分
	\begin{array}{cc}
		\underbrace{\rule{17mm}{0mm}}_m &
		\underbrace{\rule{17mm}{0mm}}_m
	\end{array}
\end{array}
```

# 8 多行公式

## 8.1 gather环境

1. `gather`环境可以实现多行公式排版，使用`\\`进行换行，每行公式都会编号

$$
\begin{gather}
	a+b=b+a \\
	ab ba
\end{gather}
$$

```latex
\begin{gather}
	a+b=b+a \\
	ab ba
\end{gather}
```

2. `gather*`环境下，每行公式不会自动编号

$$
\begin{gather*}
	3+5 = 5+3 = 8 \\
	3 \times 5 = 5 \times 3
\end{gather*}
$$

```latex
\begin{gather*}
	3+5 = 5+3 = 8 \\
	3 \times 5 = 5 \times 3
\end{gather*}
```

3. `gather`环境中，也可以在行尾加上`\notag`阻止自动编号

$$
\begin{gather}
	3^2 + 4^2 = 5^2 \notag \\
	5^2 + 12^2 = 13^2 \notag \\
	a^2 + b^2 = c^2
\end{gather}
$$

```latex
\begin{gather}
	3^2 + 4^2 = 5^2 \notag \\
	5^2 + 12^2 = 13^2 \notag \\
	a^2 + b^2 = c^2
\end{gather}
```

## 8.2 align环境

- `align`环境可以实现根据等号左对齐

1. 带编号：`align`，使用`&=`实现对齐

$$
\begin{align}
	x &= t + \cos t + 1 \\
	y &= 2 \sin t
\end{align}
$$

```latex
\begin{align}
	x &= t + \cos t + 1 \\
	y &= 2 \sin t
\end{align}
```

2. 不带编号：`align*`

$$
\begin{align*}
	x &= t & x &= \cos t & x &= t \\
	y &= 2t & y &= \sin(t+1) & y &= \sin t
\end{align*}
$$

```latex
\begin{align*}
	x &= t & x &= \cos t & x &= t \\
	y &= 2t & y &= \sin(t+1) & y &= \sin t
\end{align*}
```

## 8.3 split环境

- `split`环境可以实现等号居中对齐

$$
\begin{equation}
	\begin{split}
		\cos 2x &= \cos^2 x - \sin^2 x \\
				&= 2\cos^2 x - 1
	\end{split}
\end{equation}
$$

> :star2:如需多行公式使用同一个编号，可以在公式外套一层`equation`

```latex
\begin{equation}
	\begin{split}
		\cos 2x &= \cos^2 x - \sin^2 x \\
				&= 2\cos^2 x - 1
	\end{split}
\end{equation}
```

## 8.4 cases环境

- `cases`环境可以实现分段函数

$$
\begin{equation}
	D(x) = \begin{cases}
		1, & {如果\ } x \in \mathbb{Q}; \\
		0, & {如果\ } x \in \mathbb{R} \setminus \mathbb{Q}.
	\end{cases}
\end{equation}
$$

```latex
\begin{equation}
	D(x) = \begin{cases}
		1, & {如果\ } x \in \mathbb{Q}; \\
		0, & {如果\ } x \in \mathbb{R} \setminus \mathbb{Q}.
	\end{cases}
\end{equation}
```

> 注：在`Markdown`中，中文前不加`\text`也可以正常显示，`\text`可用来将字体摆正

# 9 运算符

## 9.1 普通运算符

1. 单运算符

$$
+, -, \times, \cdot, \pm, \mp \\
><, \ge, \le, \gg, \ll, \ne, \approx, \equiv \\
\cap, \cup, \in, \notin, \subseteq, \subsetneqq, \varnothing \\
\forall, \exists, \nexists, \because, \therefore \\
\mathbb R, \R, \Q, \N, \Z_+, \mathcal F, \mathscr F \\
\infty, \partial, \nabla, \propto, \degree \\
$$

```latex
+, -, \times, \cdot, \pm, \mp \\
><, \ge, \le, \gg, \ll, \ne, \approx, \equiv \\
\cap, \cup, \in, \notin, \subseteq, \subsetneqq, \varnothing \\
\forall, \exists, \nexists, \because, \therefore \\
\mathbb R, \R, \Q, \N, \Z_+, \mathcal F, \mathscr F
\infty, \partial, \nabla, \propto, \degree \\
```

2. 其他运算符
> :star2:在符号后加上`\limits`可以将范围显示在符号下侧

$$
\lim\limits_{x \to 0} \dfrac{x}{\sin x} \\
$$

$$
\arg\max\limits_{y \in \mathbb Y} P(x, y)
$$

$$
\text{MSE}(x)
$$

```latex
\lim\limits_{x \to 0} \dfrac{x}{\sin x} \\
\arg\max\limits_{y \in \mathbb Y} P(x, y)
\text{MSE}(x) % 直立体
```

## 9.2 大型运算符

1. 求和、求积

> 运算符下标：`_{}`，运算符上标：`^{}`

$$
\sum, \prod \\
\sum_i, \sum_{i=0}^N \\
\dfrac{\sum\limits_{i=1}^n x_i}{\prod\limits_{i=1}^n x_i}
$$

```latex
\sum, \prod \\
\sum_i, \sum_{i=0}^N \\
\dfrac{\sum\limits_{i=1}^n x_i}{\prod\limits_{i=1}^n x_i}
```

2. 积分

$$
\int, \iint, \iiint, \oint, \oiint \\
\int_{-\infty}^0 f(x) \, \text d x
$$

```latex
\int, \iint, \iiint, \oint, \oiint \\
\int_{-\infty}^0 f(x) \, \text d x
```

# 10 标注符号

1. 单字符

$$
\vec x, x', x'',\dot x, \ddot x \\
\bar y,\  \hat y,\  \tilde y \\
$$

```latex
\vec x, x', x'',\dot x, \ddot x \\
\bar y,\  \hat y,\  \tilde y \\
```

2. 多字符

$$
\overline {AB},\  \overline {xyz} \\
\overrightarrow {AB},\  \overrightarrow {xyz}
$$

```latex
\overline {AB},\  \overline {xyz} \\
\overrightarrow {AB},\  \overrightarrow {xyz}
```

# 11 箭头

$$
\leftarrow, \leftrightarrow \\
\Rightarrow, \Leftrightarrow \\
\longrightarrow, \Longrightarrow \\
\Uparrow, \Downarrow \\
\nearrow, \searrow \\
\rightharpoonup, \leftharpoondown, \rightleftharpoons
$$

```latex
\leftarrow, \leftrightarrow \\
\Rightarrow, \Leftrightarrow \\
\longrightarrow, \Longrightarrow \\
\Uparrow, \Downarrow \\
\nearrow, \searrow \\
\rightharpoonup, \leftharpoondown, \rightleftharpoons
```

# 12 括号与定界符

1. 括号

$$
([]), \{\} \\
\lceil, \rceil, \lfloor, \rfloor, ||
$$

```latex
([]), \{\} \\
\lceil, \rceil, \lfloor, \rfloor, ||
```

2. 定界符
> :star2:定界符大小自适应：使用`\left`和`\right`
$$
\left(0, \frac 1 a \right] \\
$$

```latex
\left(0, \frac 1 a \right] \\
```

$$
\left.\frac {\partial f}{\partial x} \right|_{x=0}
$$

```latex
\left.\frac {\partial f}{\partial x} \right|_{x=0}
```

# 13 latex实例

**实例一：**
$$
f(x) = \frac 1 {\sqrt{2\pi} \sigma} \rm e^{-\frac{(x-\mu)^2}{2\sigma^2}}
$$

```latex
f(x) = \frac 1 {\sqrt{2\pi} \sigma} \rm e^{-\frac{(x-\mu)^2}{2\sigma^2}}
```

> :star2:也可以使用`\exp`实现指数函数

$$
f(x) = \frac 1 {\sqrt{2\pi} \sigma} \exp \left[{-\frac{(x-\mu)^2}{2\sigma^2}}\right]
$$

```latex
f(x) = \frac 1 {\sqrt{2\pi} \sigma} \exp \left[{-\frac{(x-\mu)^2}{2\sigma^2}}\right]
```

**实例二：**
$$
\lim\limits_{N \to \infty} P 
	\left\{
		\left|
			\frac{I\left( \alpha_i \right)}{N} - H(s)
		\right| < \varepsilon
	\right\} = 1
$$

```latex
\lim\limits_{N \to \infty} P 
	\left\{
		\left|
			\frac{I\left( \alpha_i \right)}{N} - H(s)
		\right| < \varepsilon
	\right\} = 1
```

**实例三：**
$$
x(n) = \frac 1 {2\pi} \int_{-\pi}^\pi 
		X({\rm e}^{{\rm j}\omega}) {\rm e}^{{\rm j}\omega n}
		\, {\rm d} \omega
$$

```latex
x(n) = \frac 1 {2\pi} \int_{-\pi}^\pi 
		X({\rm e}^{{\rm j}\omega}) {\rm e}^{{\rm j}\omega n}
		\, {\rm d} \omega
```

**实例四：**
$$
\begin{align}
	\vec B \left( \vec r \right)
	&= \frac {\mu_0}{4\pi} \oint_C \frac{I\,{\rm d}\vec l \times \vec R}{R^3} \notag \\
	&= \frac {\mu_0}{4\pi} \int_V \frac{\vec J_V \times \vec R}{R^3} \, {\rm d} V'
\end{align}
$$

```latex
\begin{align}
	\vec B \left( \vec r \right)
	&= \frac {\mu_0}{4\pi} \oint_C \frac{I\,{\rm d}\vec l \times \vec R}{R^3} \notag \\
	&= \frac {\mu_0}{4\pi} \int_V \frac{\vec J_V \times \vec R}{R^3} \, {\rm d} V'
\end{align}
```

