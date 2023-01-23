---
aliases: [Angular Frequency, f]
creation date: 2022-12-30 13:12
modification date: Friday 30th December 2022 13:12:31
---

## The Basics

>[!question]- What is Normalized Frequency
>- Normalized Frequency $f$ (unitless): $$f=\frac{F}{F_s}$$
>	- Where 
>		- $F$ is the winding frequency of the [[Fourier Transform]] in Hz.
>		- $F_s$ is the Sampling Frequency in Hz, and $T_s$ is the Sampling Interval/Period in Seconds/Revolution.
>	- Typically restricted to a range of $0\le f  < 1$, because of the periodicity of the sinusoids, often restricted further due to [[Aliasing]]
>	- Sometimes rewritten equivalently as $-\frac{1}{2}\le f < \frac{1}{2}$ 
>	- Negative frequency causes $-jsin(..)$ and $cos(..)$. In other words, we rotate in the opposite direction as before.
>- However, some usages define it in *radians*, aka **Angular Frequency**, by squashing $j2\pi f$ into $j \omega$:  $$\omega= 2\pi \frac{F}{F_s}=2\pi f$$
>	- Where $0\le \omega < 2\pi$      radians
>
>

>[!note]- Where does Normalized Frequency come from?
> - Normalized frequency is a result of the transition from a continuous-time to a discrete time representation.
>	- In CT, we might write a [[Complex Sinusoid]] as 
>	$$\large e^{j2\pi Ft}$$
> 	- Where:
>		- $F$ is the winding frequency in revolutions/second (Hz) (because of the addition of the $2\pi$, the radian part is extracted out of F). For more info on this "winding frequency" see [[Fourier Transform]].
>		- $t$ is CT. Our input variable. $Ft2\pi$ yields the current rotational position in radians. 
>	- In DT, we want to abstract away $t$ for $n$, so we use the relation, $\large t=T_{s}n$. This comes from the fact that each value of t is separated by an integer multiple ($n$) of sampling periods ($T_{s}$)
>	- Typically, though, it's unwieldy to have to consider the sampling period of our system or our signal whenever we want to do this math
>	- $\large t=\frac{n}{F_{s}}$
> 	- Substitute: $\large \frac{F}{F_s}n$
>	- Redefine terms: $\large \frac{F}{F_{s}}=f$ 



> Bad times have a scientific value. These are occasions a good learner would not miss.
> — <cite>Ralph Waldo Emerson</cite>
