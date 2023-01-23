---
aliases: [DTFT, Spectrum, Discrete-Time Fourier Transform]
creation date: 2022-12-30 14:31
modification date: Friday 30th December 2022 14:31:52
---

## The Basics of the DTFT

>[!abstract]- The DTFT:
>The DTFT is a [[Discrete-Time Signal|DT]] version of the [[Fourier Transform]], often using [[Normalized Frequency]], $f$.
>$$\LARGE X(e^{j2\pi f})=\sum\limits_{n=-\infty}^{\infty}x[n]e^{-j2\pi fn}$$
>- The DTFT is also known as the *Spectrum* of a Signal or Sequence.
>- The DTFT is a *continuous* function of frequency.
>
>The Inverse DTFT:
>$$\LARGE x[n]=\int\limits_{-0.5}^{0.5}X(e^{j2\pi f})e^{j2\pi f}df$$
>- Note that the integral limits of [[Normalized Frequency]] could be different depending on the desired range. As long as an entire period is captured, and you are being consistent, it shouldn't matter too much.

>[!note]- Periodicity of the DTFT
> Note that the DTFT is *periodic*. Since it is a sum of sinusoids, which all have frequency multiples of $2\pi$, the longest period will be when $n=1$, such that $\large e^{-j2\pi f}$. This specific [[Complex Sinusoid]] has a period of $2\pi$, so it will go through a full period every full integer multiple of $f$. **Therefore, we only need to plot a range of $f=[0,1)$ or $f=[-0.5,0.5)$**

>[!faq]- Example (*Analysis*)
>- Let $x[n]=\{1,1,1,1\}$ (0 otherwise) and $n=0..3$. Find the DTFT of the given signal
>- DTFT: $\large X(e^{j2\pi f})=\sum\limits_{n=-\infty}^{\infty}x[n]e^{-j2\pi fn}$
>- Because $x[n]$ is 0 outside of $0\le n \le 3$, we can simplify the sum neatly: $=x[0]e^{-j2\pi f0}+x[1]e^{-j2\pi f1}+x[2]e^{-j2\pi f2}+x[3]e^{-j2\pi f3}$
>- Subbing in the values for $x[n]$, we get: $X(e^{j2\pi f})=1+e^{-j2\pi f}+e^{-j4\pi f}+e^{-j6\pi f}$
>- Notice that our output of the DTFT function is a *continuous* function of frequency.
>![[Pasted image 20230113213455.png|750]]
>MATLAB Code:
>```
>f=0:0.01:1; % normalized freq
X=1+exp(-j*2*pi*f)+exp(-j*2*pi*f*2)+exp(-j*2*pi*f*3);
plot(f,abs(X));
xlabel("Normalized Frequency");
ylabel("Complex Magnitude of the DTFT");
>```

## Interpreting the Spectrum

>[!success]+ The Spectrum
>- A "Spectrum" is the DTFT of a Signal or Sequence. Typically if it's the DTFT of a System's [[Impulse Response]], we call it a [[Frequency Response]] instead.
>- Typically broken into two parts:
>	- Amplitude Spectrum: $|Y (e^{j2\pi f})|=|H (e^{j2\pi f})||X (e^{j2\pi f})|$
>	- Phase Spectrum: $\angle Y (e^{j2\pi f})=\angle H (e^{j2\pi f})+\angle X (e^{j2\pi f})$
>- Depending on what you are working with, you may be more or less concerned with the phase spectrum.
>	- For instance, in audio applications, we hear amplitude, but not phase.



## Comparison between Domains and Signals/System

> Friendship... is not something you learn in school. But if you haven't learned the meaning of friendship, you really haven't learned anything.
> — <cite>Muhammad Ali</cite>



