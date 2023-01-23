---
aliases: [Discrete Fourier Transform]
creation date: 2022-12-30 15:32
modification date: Friday 30th December 2022 15:32:22
---
## The Basics

>[!quote]- Definition
> >"In mathematics, the discrete Fourier transform (DFT) converts a finite sequence of equally-spaced samples of a function into a same-length sequence of equally-spaced samples of the discrete-time Fourier transform (DTFT), which is a complex-valued function of frequency."
 >\-https://home.engineering.iastate.edu/~julied/classes/ee524/LectureNotes/l5.pdf

>[!abstract]- Equation
>- The DFT is the primary interval of the [[DFS]], and is a sampling of the [[DTFT|DTFT]].
>$$\begin{array}\\\LARGE X_N[k]=\sum\limits_{n=0}^{N-1}x[n]e^{-j\frac{2\pi }{N} kn}\\\text{N-Point DFT}\end{array}$$
>- Where:
>	- N is the number of points in the DFT (you often choose this)
>		- **Zero-padding**: In the case that $x[n]$'s non-zero range is smaller than N, we add on additional zeros to $x[n]$. I.e. $X_8$ would mean our input $x[n]=\{4,3,2,1\}$ would turn into $x[n]=\{4,3,2,1,0,0,0,0\}$ so that our DFT length could be found. MATLAB automatically assumes this is true when you try to calculate a DFT with more points than n values.
>	- **High-resolution vs. High Density**: More points will produce a DFT that more closely resembles the [[DTFT|DTFT]] (high-density), but does not reveal data that was not already in the [[DTFT|DTFT]]. To get a high-resolution spectrum, you will need to get more samples from the original signal.
>	- k is which point of the DFT we are calculating, such that $\bf{0\leq k\leq (N-1)}$
>- Evaluates the [[DTFT|DTFT]] at discrete points, k, and calls each point $X[k]$ 
>- Unlike the [[DTFT|DTFT]], the DFT is not Continuous in Frequency, the **DFT has N discrete values.**
>![[Pasted image 20221230162558.png]]
>

>[!FAQ]- Examples
>#### Example Calculation
>![[302 DFT Example.PNG]]
>#### Zero-Padded DFT
>![[302 Zero-padded DFT.png]]

>[!question]- Example (*Analysis*)
>- Building on the example from the [[DTFT]] page, let's find the 4 point and 8 point DFT of the sequence, $x[n]=\{1,1,1,1\}$
>- Insert maths here
>- Here's a MATLAB plot of the DTFT, aswell as the 4 point (Green Fill), and 8 point (Red Circle) DFT. As you can see, the DFT is a sampling of the DTFT in frequency. 
>![[Pasted image 20230114012112.png|800]]
>```
>f=0:0.01:1; % normalized freq
>x=[1,1,1,1];
>X=1+exp(-j*2*pi*f)+exp(-j*2*pi*f*2)+exp(-j*2*pi*f*3); %DTFT of x
>X4=fft(x,4);
>f4=0:1/4:1-1/4;
>X8=fft(x,8);
>f8=0:1/8:1-1/8;
>plot(f,abs(X),f4,abs(X4),'x',f8,abs(X8),'o');
>xlabel("Normalized Frequency");
>ylabel("Complex Magnitude of the Fourier Transform");
>```


> Happiness mainly comes from our own attitude, rather than from external factors.
> — <cite>Dalai Lama</cite>



