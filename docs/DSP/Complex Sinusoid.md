---
aliases: [Eulers Formula, Phasers]
creation date: 2022-12-29 22:22
modification date: Thursday 29th December 2022 22:22:42
---

>[!cite] ## Euler's Formula
>$$\LARGE e^{ix}=cos(x)+isin(x)$$
>- Euler's formula basically states that a exponential raised to a imaginary value has both a real and a imaginary component
>- If we map the axis such that vertical is Imag. and horizontal is real, we find that our exponential raised to a imaginary value will appear to rotate CCW with increasing constant values, hence the sine and cosine
>- The *magnitude* of the complex value is **constant**. In other words, the only thing that is changing is the *phase*.
>	- Remember that complex magnitude discards j: $\sqrt{cos^2(x)+sin^2(x)}=\sqrt{1}=1$, such that the magnitude of the the exponential will be 1 if there is no coefficient.
>- The exponential rotates with a periodicity of $x=2\pi$

>[!hint]+ Complex Sinusoid
>Here is our DSP Complex Sinusoid:
>$$\LARGE x[n]=Xe^{j2\pi fn}$$
>- X is a complex **constant**
>- $f$ is [[Normalized Frequency]]
>- Note that the magnitude of the exponential term is always 1, so the magnitude at any n will be equal to X. In other words, **X is the complex magnitude of the sinusoid**
>	- Since X does not vary with n, the magnitude of this complex sinusoid will be constant!
>	- Notice that $\large e^{-j \frac{\pi}{2}}=cos(\frac{\pi}{2})+jsin(\frac{\pi}{2})=0+j$ 

> A goal without a plan is just a wish.
> — <cite>Larry Elder</cite>



