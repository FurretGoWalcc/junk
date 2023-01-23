---
aliases: []
creation date: 2023-01-01 17:40
modification date: Sunday 1st January 2023 17:40:13
---
In essence, the Fourier transform is the decomposition of signals into a sum of [[Complex Sinusoid]]s of varying frequencies. With a frequency representation, we get a clearer representation of the signal's makeup. For instance, if we took a Fourier Transform of an audio signal, we might be able to easily see noise at 60 Hz from the power grid. As with most transforms, we can go both ways; towards frequency (*Analysis*) and towards time (*Synthesis*/*Inverse*).

---
## The Basics

>[!cite]- A helpful 3Blue1Brown Video
><iframe width="840" height="472.5" src="https://www.youtube.com/embed/spUNpyF58BY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

>[!done]- Why Fourier is Important
>![[Pasted image 20230101174600.png]]
>- Fourier transforms are all about taking a signal or sequence and thinking about it as a series (sum) of sine and cosine waves.
>- Oftentimes we only see the sum of all the smaller components (the yellow line above)
>- Typically, our goal is to: 
>	- **1. Identify frequency makeup (the individual sinusoids which could represent our signal)**
>	- **2. Do something to a particular group of frequencies, in which case we need a frequency representation of a signal so that we can scale desired portions appropriately.****

>[!hint]- Building the Continuous Fourier Transform from the Ground-Up
>![[Pasted image 20230102144235.png]]
>- 3Blue1Brown shows it in a pretty elegant way in this picture.
>	- At the top, we have the input signal. It's got a constant frequency or set of frequencies.
>	- On the bottom left, we have a 2D graph on the Complex Plane.
>		- We create this graph by "winding"- using the amplitude of the graph sampled at some *other frequency*. You can visually see the periods of this other frequency as the dotted lines on the top graph.
>		- Rotating with the other frequency, the radius from the origin at each angle is determined by the sampled real magnitude of the input. 
>		- Then we look at the *center of mass* about the plane. If the center of mass is near the origin, that means that the frequency we are winding with does not have a strong correlation with any particular amplitude. If it is leaning to one side, that means that we have roughly the same amplitude in the same places every revolution.  
>	- On the bottom right, we have the *real* value of the center of mass of the circle. 
>		- As we change the winding frequency, we begin to see the full picture- where the center of mass has little to no correlation, and where it is strongly pulled to one direction. In this way we can differentiate between the different frequencies. 
>		- If we do this continuously, we are essentially creating the [[DTFT|Spectrum]].
>  - Roughly speaking, $$\begin{array}{} X(e^{j2\pi F})\approx \frac{1}{(t_2-t_1)}\int\limits_{t_1}^{t_2}g(t)e^{-j2\pi Ft}dt\\\text{The "Almost" Continious Time Fourier Transform}\end{array}$$
>  - In other words, the Fourier Transform is essentially really just the mean of a function that is rotated around a circle at $F$ cycles/second over time interval $t_{2}$ to $t_1$
>  - The only real distinction is that rather than the average over time, we usually just find the total sum. This is just a scaling difference, so the graph is essentially the same.
>  - The negative in the complex exponential is there because the convention is to rotate CW rather than CCW.
>  $$\LARGE \begin{array}{} X(e^{j2\pi F}) = \int\limits_{t_1}^{t_2}g(t)e^{-j2\pi Ft}dt\\\text{The Continious Time Fourier Transform}\end{array}$$
>  - Keep in mind that the Fourier Transform typically produces *Complex* coefficients, so oftentimes you will need to explicitly find the *Magnitude* to correctly work with in the frequency domain.

---
## Discrete Fourier

>[!danger]- Continuous-Time to a Discrete-Time Representation
>- Oftentimes in reality, we are *sampling* a real thing to obtain a partial understanding of a continuous thing -> Continuous input $g(t)$ replaced with [[Discrete-Time Signal|DT]] input $x[n]$.   
>- Due to sampling, the notion of [[Normalized Frequency]] results from substituting $\large \frac{n}{F_{s}}$ for $t$
>- This also brings in issues related to [[Aliasing]]
>- Since we are really just evaluating at specific values of $n$, we can simplify the integral into a sum at integer multiples of $n$.
>- The [[DTFT|Discrete-Time Fourier Transform]] is almost exactly the same as the Continuous Time version described above. See it's page for more details
>$$\begin{array}{}\LARGE X(e^{j2\pi f})=\sum\limits_{n=-\infty}^{\infty}x[n]e^{-j2\pi fn}\\\text{The DTFT}\end{array}$$

>[!success]- Discrete (Time and Frequency) Fourier Transform
>- If we take sample the [[DTFT]] on it's frequency axis, we get the [[DFS|Discrete Fourier Series]] and [[Discrete Fourier Transform]], which are Discrete in both Time and Frequency. Typically, these (particularly the DFT) are used, because they are much easier for computers to calculate than the continuous DTFT
>$$\begin{array}{}\LARGE X[k]=\sum\limits_{n=0}^{N-1}x[n]e^{-jk \frac{2\pi}{N}n}\\\text{The DFS and DFT (Analysis Equation)}\end{array}$$
>- Where $X[k]$ is the k-th coefficient of the DFT/DFS, j is the imaginary unit, and the sum is taken over the length of one period of the sequence (DFS) or the length of the sequence (DFT). 
>- DFS describes *infinite-length, periodic* signals, whereas the DFT describes *finite-length* signals. A good discussion can be seen here, https://dsp.stackexchange.com/a/18157. The output of this equation will be the exact same for a DFT and a DFS.

>[!note]- What Fourier do I apply? 
>![[Pasted image 20230113021230.png]]

---
## Domain Comparison

| Item   | [[Discrete-Time Signal\|Discrete-Time]] | Frequency                                                     |
| ------ | --------------------------------------- | ------------------------------------------------------------- |
| System | $h[n]$ [[Impulse Response]]             | $\large H(e^{j2\pi f})$ [[Frequency Response]]                |
| Signal | $x[n]$ Sequence                         | $\large X(e^{j2\pi f})$ [[DTFT\|Spectrum]]                    |
| Output | $y[n]=x[n]\ast h[n]$ [[Convolution]]    | $Y(e^{j2\pi f})=H(e^{j2\pi f})X(e^{j2\pi f})$ Multiplication! |
| Units  | Units                                   | Units/Normalized Freq                                         |


> If opportunity doesn't knock, build a door.
> — <cite>Milton Berle</cite>



