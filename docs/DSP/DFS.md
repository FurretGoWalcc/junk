---
aliases: [Discrete Fourier Series, DTFS, DFS]
creation date: 2022-12-30 22:13
modification date: Friday 30th December 2022 22:13:01
---

>[!quote]-  Helpful Resource (DTFT, DFS, DFT)
>https://ethz.ch/content/dam/ethz/special-interest/mavt/dynamic-systems-n-control/idsc-dam/Lectures/Signals-and-Systems/Lectures/Fall2018/SigSys_Lect5.pdf

---
## The Basics

>[!tip]- DFT/DFS Representation of a Periodic Signal
>The Discrete Fourier Series perfectly represents a *periodic* sequence $x[n]$ as a series (sum) of sinusoids (or [[Complex Sinusoid]]s). 
>- Below is the complex forms of the *Synthesis* (Discrete Frequency to Discrete Time), and *Analysis* (Discrete Time to Discrete Frequency)
>$$\begin{array}{}\LARGE x[n]=\frac{1}{N}\sum\limits_{k=0}^{N-1}X[k]e^{j2\pi \frac{k}{N}n}\\\text{Synthesis Equation, IDFS}\\\LARGE X[k]=\sum\limits_{n=0}^{N-1}x[n]e^{-jk \frac{2\pi}{N}n}\\\text{Analysis Equation, DFS}\end{array}$$
>- Since $x[n]$ is periodic, so is the DFS, with period N.
>- The lowest frequency sinusoid of the DFS is $\large \frac{2\pi}{N}$, aka the **fundamental frequency**
>- *We need N complex exponentials to represent a [[Discrete-Time Signal|DT]] periodic signal with period N.*
>- Aka [[Discrete-Time Signal|Discrete-Time]] Fourier Series (DTFS)

>[!question]- Example Coefficient Calculation (*Analyzing* Frequency Content of a Sequence)
>Given the periodic sequence, $x[n]=\{...,2,0,4,-5,2,0,4,-5,2,0,4,-5,...\}$, and that the first -5 is n=0 find the DFS coefficients $X[k]$.
>(Alternative prompt for DFT: Given a sequence defined below, find the DFT coefficients for the sequence)
>$$x[n]=\Bigl\{ \begin{array}{l}{-5,2,0,4},\; \text{ for } 0\le n <N \\0,\; otherwise\end{array}$$
>1. The pattern repeats every 4 n, so N=4.
>2. DFS Coefficients Definition: $\large X[k]=\sum\limits_{n=0}^{N-1}x[n]e^{-jk \frac{2\pi}{N}n}$
>3. Apply N=4: $\large X[k]=\sum\limits_{n=0}^{3}x[n]e^{-jk \frac{2\pi}{4}n}$
>
>5. Evaluate Sum: $\large =x[0]e^{-jk \frac{2\pi}{4}0} + x[1]e^{-jk \frac{2\pi}{4}1} + x[2]e^{-jk \frac{2\pi}{4}2} + x[3]e^{-jk \frac{2\pi}{4}3}$
>   
>6. Simplify: $=\large -5(1) + 2e^{-jk \frac{\pi}{2}} + 0e^{-jk\pi} + 4e^{-jk \frac{3\pi}{2}}$
>	1. $\large X[k]=-5 + 2e^{-jk \frac{\pi}{2}} + 4e^{-jk \frac{3\pi}{2}}$
>	   
>7. Find $\{X[k]\}$: 
>	1. $\large X[0]=-5 + 2e^{-j0 \frac{\pi}{2}} + 4e^{-j0 \frac{3\pi}{2}} = -5+2+4=1$
>	2. $\large X[1]=-5 + 2e^{-j\frac{\pi}{2}} + 4e^{-j\frac{3\pi}{2}} = -5+2(-j)+4(+j)=-5+2j$
>	3. $\large X[2]=-5 + 2e^{-j2\frac{\pi}{2}} + 4e^{-j2\frac{3\pi}{2}} = -5+2(-1)+4(-1)=-11$
>	4. $\large X[3]=-5 + 2e^{-j3\frac{\pi}{2}} + 4e^{-j3\frac{3\pi}{2}} = -5+2(+j)+4(-j)=-5-2j$
>	   
>8. Answer: $X[k]=\{1,-5+2j,-11,-5-2j\}$

>[!question]- But what do the coefficients mean? (*Synthesizing* a signal from it's frequency content)
>- Let's use the previous example's coefficients:  $X[k]=\{1,-5+2j,-11,-5-2j\}$
>- The Synthesis equation: $$\LARGE x[n]=\frac{1}{N}\sum\limits_{k=0}^{N-1}X[k]e^{j2\pi \frac{k}{N}n}$$
>- If we manually build the sinusoid form of those coefficients using [[Complex Sinusoid|Eulers Formula]], we'll find that all of the imaginary parts of the our equation will either cancel out or be zero-valued for integer values of n, leaving us with just the real portions at our sampling points:
>  $$\large x[n]=1-5cos(2\pi \frac{n}{4})-11cos(2\pi \frac{n}{2})-5cos(2\pi \frac{3n}{4})-2sin(2\pi \frac{n}{4})+2sin(2\pi \frac{3n}{4})$$
>- Here is the graphical representation of the added real series (lined) and the original sequence (circles). Keep in mind that we could have also graphed the complex magnitude of the DFT, or graphed the imaginary part on it's own. 
>![[fourierseriesvsperiodicsequence.png|1200]]
>```matlab
>clear all
>x=[-5 2 0 4];
> m=0:3;
> n=0:0.1:3;
>y=1-5*cos(2*pi*n/4)+-11*cos(2*pi*n/2)+-5*cos(2*pi*3*n/4)-2*sin(2*pi*n/4)+2*sin(2*pi*3*n/4);
>plot(m,x,'o',n,y/4,'x');
>title("Real Fourier Series vs Real Periodic Sequence")
>xlabel("Discrete Time, n");
>ylabel("Amplitude")
>ylim([-5.5,4.5]);
>xlim([-0.5,3.5]);
>```
---

> What we think, we become.
> — <cite>Buddha</cite>



