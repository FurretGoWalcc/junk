---
aliases: [Nyquist Frequency]
creation date: 2022-12-30 13:23
modification date: Friday 30th December 2022 13:23:42
---
## Basics

>[!summary]- What is Aliasing
>- Aliasing is an effect of our [[Discrete-Time Signal|Discrete-Time]] definition that causes different signals to become indistinguishable (aliases of one another, when sampled)
>- In the example below, these two *different* waveforms appear identical when sampled
>	- ![[Pasted image 20221230134039.png]]
>- In other words, there's multiple solutions which satisfies the $x[n]$ for any given problem.
>

>[!danger]- When does Aliasing Occur + The *Nyquist Frequency*
>- Aliasing occurs when $$\large F_{signal} \ge \frac{F_{s}}{2}$$
>- The **Nyquist Frequency** $\large F_\text{Nyquist}=2|F_\text{signal}|<F_s$ defines the minimum which the sampling frequency must exceed to avoid aliasing, aka the maximum input frequency at a given sampling frequency to avoid aliasing.


> We could never learn to be brave and patient if there were only joy in the world.
> — <cite>Helen Keller</cite>



