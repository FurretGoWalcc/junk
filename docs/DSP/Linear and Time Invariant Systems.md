---
aliases: [LTI, TI, L, Shift Invariant]
creation date: 2022-12-29 14:55
modification date: Thursday 29th December 2022 14:55:11
---
A LTI system is both Linear and Time Invariant.
>[!Note]- Linear
>A linear system is additive and homogenous. 
>>[!tip] Additive
>>- Requires that for any two inputs $x_{1}[n]$ and $x_{2}[n]$, where $Lx_1[n]\rightarrow y_1[n]$ and given system L $Lx_2[n]\rightarrow y_2[n]$:
>>	$$Lx=y\rightarrow L(x_1+x_2)\ne y_1+y_2$$
>>- Aka, replace x with the two inputs, then set them equal to the sum of the two inputs.
>>- Basically, this test fails if the [[Difference Equation]] is not a linear one (i.e. sinusoidal or exponential) or if there is a intercept that does not scale with the input.
>
>>[!warning] Homogenous
>>- Requires that for any scalar k and input x, $kx\rightarrow ky$. This will fail when there is an intercept or input invariant part. 
>>$$kx[n]+1\ne k(x[n]+1)$$

>[!Bug]- Time Invariant
>- A delay in the input results in a corresponding delay in the output. 
>- E.g. given system L, input x, and output y, 
> $$Lx=y \rightarrow Lx[n-m]=y[n-m]$$

> Always be yourself, express yourself, have faith in yourself, do not go out and look for a successful personality and duplicate it.
> — <cite>Bruce Lee</cite>



