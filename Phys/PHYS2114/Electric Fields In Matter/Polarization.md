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