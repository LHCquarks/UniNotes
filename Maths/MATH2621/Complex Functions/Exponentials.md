## Definition
The exponential function is defined by the power series
$$
\begin{align}
\sum_{n=0}^\infty \frac{z^n}{n!} \tag{1}
\end{align}
$$
This is simply the Taylor series for the exponential function around $0$ extended to the complex plane. 
We usually write the power series representation of the exponential function as $\exp(z)$ whilst we write the trig defined form as $e^z$. Despite the different writing conventions they are all the same. 
![[exp.png]]
## Properties
### Relation to trig
Letting $z = x + iy$ we get the formula:
$$
\begin{align}
e^z = e^x(\cos(y) + i \sin(y))
\end{align}
$$
### $\infty \rightarrow 1$ 
Because the exponential function maps the imaginary coordinate to the angle of the outputted number and that angles are cyclic we get that $z$ values that are $2ki$ apart all map the the same value and so the exponential function is infinite to one
### Old exponential laws
Just like with the real exponential function we get that:
$$
\begin{align}
e^0 &= 1 \\
e^{z + w} &= e^ze^w &\forall z,w \in \mathbb C\\
e^{-z} &= (e^z)^{-1} &\forall z \in \mathbb C\\
e^z &\not = 0 &\forall z \in \mathbb C \\
\frac{d}{dz} e^z &= e^z &\forall z \in \mathbb C \\
\end{align}
$$
Further we have the property that if $f' = f$ and $f(0) = 1$ then $f(z) = e^z$
#### Lemma
$$
e^we^z=e^{w+z} \tag{2}
$$
#### Proof
Let $w = x_1 + iy_1$ and $z = x_1 + iy_1$
$$
\begin{align}
e^we^z &= (e^{x_1}(\text{cos}(y_1)+i\text{sin}(y_1))(e^{x_2}(\text{cos}(y_2)+i\text{sin}(y_2)) \tag{1}\\
&= e^{x_1}e^{x_2}(\text{cos}(y_1)+i\text{sin}(y_1)(\text{cos}(y_2)+i\text{sin}(y_2) \\
&= e^{x_1 +x_2}(\text{cos}(y_1)\text{cos}(y_2) + i\cos(y_1)\sin(y_2) + i\sin(y_1)\cos(y_2) - \sin(y_1)\sin(y_2)) \\
&= e^{x_1 +x_2}((\text{cos}(y_1)\text{cos}(y_2) - \sin(y_1)\sin(y_2)) + i(\cos(y_1)\sin(y_2) + \sin(y_1)\cos(y_2))) \\
&= e^{x_1 +x_2}(\cos(y_1+y_2) + i\sin(y_1+y_2)) \\
&=e^{x_1+x_2+i(y_1+y_2)} \\
&= e^{x_1+iy_1 + x_2 + iy_2} \\
&= e^{w + z}
\end{align}
$$

### Magnitude
#### Lemma
If $z\in \mathbb{C}$  then 
$$
|e^{z}| = e^{\text{Re}(z)}
$$
#### Proof
$$
\begin{align}
|e^z| &= |e^x(\cos(y)+i\sin(y))| \tag{1} \\
&= |e^x||\cos(y)+i\sin(y)| \\
&= |e^{\text{Re}(z)}|\sqrt{cos^2(y)+\sin^2(y)} \\
&= e^{\text{Re}(z)}\sqrt{1} \\
&= e^{\text{Re}(z)}
\end{align}
$$
## Other facts
### $|e^{i\theta} - 1| \leq |\theta|$
#### Proof

## Inverse
The inverse of the exponential function is $\log(z)$