Materials can generally be sorted into two types **Dielectrics / Instructors** and **Conductors**.

Whilst a conductors charges are free to move about the material dielectrics's charges are held on a tight leash and can not move much. Usually for dielectrics this means that the electrons in the atoms are confined to the atom and not free to traverse the lattice. 

## Induced dipoles
When an external electric field is applied to an atom the electron cloud is drawn in the opposite direction to the electric field whilst the nucleus is drawn in the direction of the electric field thus forming a dipole. As it turns out it is fairly accurate to approximate this relationship with
$$
\begin{align}
\vec p &= \alpha \vec E
\end{align}
$$
for most simple atoms with the constant $\alpha$ being the **atomic polarizability** of the molecule determined experimentally.

For molecules that are more complicated and do not benefit from symmetry we have to alter our formula as different axis have different $\alpha$. This can be done with the matrix formula
$$
\begin{align}
\vec p &= \pmatrix{
\alpha_{xx} & \alpha_{xy} & \alpha_{xz} \\
\alpha_{yx} & \alpha_{yy} & \alpha_{yz} \\
\alpha_{zx} & \alpha_{zy} & \alpha_{zz} \\
} \vec E
\end{align}
$$
In the above formula the matrix is called the **polarizability tensor** for the molecule and it depends on the axis of the coordinate system being used however it is always possible to find a set of principle axis so that using them the matrix becomes diagonal.

Note that in the above formula $\vec p$ is not necessarily in the same direction as $\vec E$

## Alignment of polar molecules
Some molecules posses a natural polarization and thus they will experience forces within an external electric field. If the electric field is uniform across the molecule (it normally is) we can conclude that there will be no total force on the molecule however there will still be a torque given by
$$
\begin{align}
\vec N &= \vec p \times \vec E
\end{align}
$$
If however, the electric field is not uniform then there will be a net force on the molecule of
$$
\begin{align}
\vec F_{\text{total}} &= \vec F_+ + \vec F_- \\
&= q\vec E_+ - q\vec E_- \\
&= q(\Delta \vec E) \\
&= q(d \cdot \nabla)\vec E \\
&= (p\cdot \nabla) \vec E
\end{align}
$$
## Polarization of materials
Now that we have found what happens to different types of molecules we can consider what happens to groups of molecules under an external electric field.

In the case a material is made up of non-polar molecules the electric field will induce dipoles in roughly the same direction as the electric field (if the molecule's polarization is not in the same direction as the electric field the random orientations of the atoms will cancel each other out to produce only one electric field in one direction). 
In the case that the material is instead polar the electric field rotates the molecules so that $\vec p$ aligns with the electric field. Random thermal processes try to disturb this so as soon as the electric field is turned off the the molecules return back to before.

Either way we get a total polarization in the material. This total polarization depends on the volume so we define a value for our materials called the **polarizability** of the material $\vec P$ as the polarization per unit volume 