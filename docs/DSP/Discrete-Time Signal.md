---
aliases: [DT, Discrete-Time]
creation date: 2022-12-28 21:37
modification date: Wednesday 28th December 2022 21:38:30
---
>[!tip] Breaking Down the Name
> - *Discrete*: finite equally-spaced values, rather than infinitesimally smaller-spaced values.  
> - *Signal*: some action that is used to convey information or instructions. E.g. voltage, current, or power.
> - *Discrete Time*: a sampling (some portion of) *Continuous Time* 
> - *Discrete-Time Signal*: an action measured across finite equally-spaced values of time

>[!note]+ Notation
> - $x[n]$ implies x exists at discrete values of t
> 	- Typically *n* is an *integer* value.
> 	- *n* is synonymous with sample. E.g n=0 is the first sample, n=1 is the second sample...
> - $x(t)$ implies x exists at continuous values of t[^1]
> - $x[n]=x(nT_s)$ where
> 	- Ts is the *Sampling Interval*, the reciprocal of the [[Sampling Frequency]]

>[!example]- Discrete Signals
>![[Pasted image 20221228234002.png|750]]
>![[Pasted image 20221229113908.png|750]]


> Where there is charity and wisdom, there is neither fear nor ignorance.
> — <cite>Francis of Assisi</cite>

[^1]: x(t) is not necessarily guaranteed to be continuous on it's entire domain. 