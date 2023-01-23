---
aliases: [Frequency Response Characteristic]
creation date: 2022-12-30 12:14
modification date: Friday 30th December 2022 12:14:57
---

## The Basics

>[!hint]- Equation
>- The Frequency Response Characteristic is the [[Impulse Response]] of a [[Linear and Time Invariant Systems|LTI]] system to a [[Complex Sinusoid]]
>- Also known as the [[DTFT|DTFT]] of $h[n]$ and the *Frequency Response Characteristic*
>$$\LARGE H(e^{j2\pi f})=\sum\limits_{k=-\infty}^{\infty}h[k]e^{-j2\pi fk}$$
>- $H(e^{j2\pi f})$ exists for every [[Bounded Input Bounded Output Stability|BIBO Stable]] [[Linear and Time Invariant Systems|LTI]] system as well as some that are not stable
>- Is similar to [[Transfer Function]]:
>$$\large y[n]=H(e^{j2\pi f})Xe^{j2\pi fn}$$
>$$\large Xe^{j2\pi f}\xrightarrow{h[n]}Ye^{j2\pi f}$$

>[!note]- Derivation
>1. Definition of [[Impulse Response]] and [[Convolution]] $$\large y[n]=x[n]\ast h[n]=\sum\limits_{k=-\infty}^{\infty}x[n-k]h[k]$$
>2. Replace input with a [[Complex Sinusoid]] $$\large =\sum\limits_{k=-\infty}^{\infty}Xe^{j2\pi f(n-k)}h[k]$$
>3. Pull out piece which does not vary with k $$\large =Xe^{j2\pi f(n)}\bigg(\sum\limits_{k=-\infty}^{\infty}e^{-j2\pi fk}h[k]\bigg)$$
>4. Rewrite terms as freq. resp. $$\LARGE =Xe^{j2\pi fn}H(e^{j2\pi f})$$
>- The response of an [[Linear and Time Invariant Systems|LTI]] system to a **sinusoidal input will be a sinusoid with the same frequency**
>	- Because both the input and the response have the same frequency, the output will too!

>[!done]- Periodicity
>- **$H(e^{j2\pi f})$ is periodic with a period of 1**:
>	- $H(e^{j2\pi (f+1)})=H(e^{j2\pi f})$
>	- (Period of sine and cosine is 2pi, so sin(2pif) has a period of 1)
>- See [[Normalized Frequency]]

>[!question]- Examples
>#### Example Calculation using [[DTFT]] of Impulse Response
>![[Pasted image 20221230141513.png]]
>#### Example Calculation using definition of [[Complex Sinusoid]]
>![[Pasted image 20221230142709.png]]


> Let us sacrifice our today so that our children can have a better tomorrow.
> — <cite>A. P. J. Abdul Kalam</cite>



