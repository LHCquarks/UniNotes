## Definition
Let $z = x+iy$, then
$$
e^z = e^x(\text{cos}(y) + i\text{sin}(y)) \tag{1}
$$
## Properties
### $\infty \rightarrow 1$ 
Because the exponential function maps the imaginary coordinate to the angle of the outputted number and that angles are cyclic we get that $z$ values that are $2ki$ apart all map the the same value and so the exponential function is infinite to one
### Old exponential laws
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
