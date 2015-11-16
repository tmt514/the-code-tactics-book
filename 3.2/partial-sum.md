# Trick 3.2 - Partial sum

計算部分和是很重要的概念。若我們能夠預處理部分和，就可以很快速地求出很多「連續和」。具體的應用包含各種不同的（滾動）雜湊函數 rolling hash。考慮以下序列：

$$
A = a_1, a_2, \cdots, a_n
$$

我們可以令函數 $$f(x, A) = a_1 + a_2x + a_3x^2 + \cdots + a_nx^{n-1}$$ 於是我們要計算任何一個連續項的函數值：
$$
\begin{align*}
f(x, A[\ell..r]) &= a_\ell+a_{\ell+1}x+\cdots + a_rx^{r-\ell-1}\\
&= x^{\ell-1} \left(f(x, A[1..r]) - f(x, A[1..\ell-1])\right)
\end{align*}
$$

實際使用的時候我們只要儲存所有的前綴就可以了。例如各種數位統計問題，只要是要你計算 $$[\ell ..r]$$ 之間有幾個數字滿足某條件，其實只要計算 $$[1..r]$$ 減去 $$[1..\ell-1]$$ 就可以了。

## 2D Partial Sum