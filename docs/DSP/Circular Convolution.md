---
aliases: [Circular Index]
creation date: 2022-12-30 16:28
modification date: Friday 30th December 2022 16:28:17
---

>[!tip]+ Equation
>Given two sequences $x[n]$ and $h[n]$ which are both defined on n=0,1,2,...,N-1, the circular convolution $z[n]$ is
>$$\LARGE z[n]=x[n]\circledast h[n]=\sum\limits_{m=0}^{N-1}x[(m)_N]h[(n-m)_N]$$
>
>>[!danger]+ Circular Indexing
>>$(n-m)_N$ is essentially n-m modulo N. In other words, n-m can be 0,1,2,...,N-1, but upon reaching N will wrap back around to 0
>- In practice the way this n-m thing works is that $x[m]$ is a constant, and we are walking backwards through $h[n]$ as m increments
>- This can be represented and solved fairly easily in matrix form, see Examples below

>[!FAQ]+ Examples
>#### Matrix Example
>Given that $x[n]$={1,2,5} and $h[n]$={4,-3,0,9}, Compute the 4-point circular convolution.
>1. N=4 so zero pad; x[n]={1,2,5,0}.
>2. $$\begin{bmatrix}4 & -3 & 0 & 9\\9 & 4 & -3 & 0\\0 & 9 & 4 & -3\\-3 & 0 & 9 & 4\end{bmatrix}\begin{bmatrix}1\\2\\5\\0\end{bmatrix}=\begin{bmatrix}4+18+0+0=22\\-3+8+45=50\\0+-6+20+0=14\\9+0+-15+0=-6\end{bmatrix}$$
>3. $x[n] \circledast h[n] = \{22,50,14,-6\}$

> No valid plans for the future can be made by those who have no capacity for living now.
> — <cite>Alan Watts</cite>



