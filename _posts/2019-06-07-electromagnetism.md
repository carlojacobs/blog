---
layout: post
title: "Transforming the Field Tensor"
author: "Carlo Jacobs"
---

## The Lorentz Transformation in Vector Form
According to Einstein's _Special Theory of Relativity_,  different observers with different inertial reference frames will not agree on the time and place (i.e. coordinates) of a particular event. Let's say I am standing next to the highway and you are on the highway, in your car, traveling at a certain velocity $v$ in the $x$ direction. If I want to describe your coordinates in terms of my own, I have to do so using a Lorentz transformation:

<div class="equation">
$$
\begin{equation}\label{eq:simple_transform}
{\displaystyle {\begin{aligned}t'&=\gamma \left(t-{\frac {vx}{c^{2}}}\right)\\x'&=\gamma \left(x-vt\right)\\y'&=y\\z'&=z\end{aligned}}}
\end{equation}
$$

where $\left(t, x, y, z\right)$ and $\left(t^\prime, x^\prime, y^\prime, z^\prime\right)$ are the coordinates of an event in two frames, where the primed frame is seen from the unprimed frame as moving with speed $v$ along the x-axis, $c$ is the speed of light, and ${\displaystyle \gamma =\textstyle \left({\sqrt {1-{\frac {v^{2}}{c^{2}}}}}\right)^{-1}}$ is the Lorentz factor.

The transformation between different inertial reference frames can be more elegently described using 4-vectors. Let's consider an event $X^\mu$. Where $\left(t, x, y, z\right) = \left(X^0, X^1, X^2, X^3\right)$. We can now define a Lorentz matrix $L^\mu_{\,\,\nu}$ that captures the detailes of a Lorentz transformation along the $x$ axis.

<div class="equation">
$$
\begin{equation}\label{eq:lorentz_matrix}
L^\mu_{\,\,\nu} =
\begin{pmatrix}
\frac{1}{\sqrt{1-v^2/c^2}} & \frac{-v}{\sqrt{1-v^2/c^2}} & 0 & 0 \\
\frac{-v}{\sqrt{1-v^2/c^2}} & \frac{1}{\sqrt{1-v^2/c^2}} & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}
\end{equation}
$$
</div>

We can now transform the 4-vector $X^\mu$ using the Lorentz matrix and basic matrix multiplication[^1]:

<div class="equation">
$$
\begin{equation}
\left(X^\prime\right)^\mu = \sum_\nu L^\mu_{\,\,\nu} \, X^\nu = L^\mu_{\,\,\nu} \, X^\nu
\end{equation}
$$
</div>

Or:

<div class="equation">
$$
\begin{equation}
\begin{pmatrix}
X^0\\X^1\\X^2\\X^3
\end{pmatrix}^\prime
=
\begin{pmatrix}
\frac{1}{\sqrt{1-v^2/c^2}} & \frac{-v}{\sqrt{1-v^2/c^2}} & 0 & 0 \\
\frac{-v}{\sqrt{1-v^2/c^2}} & \frac{1}{\sqrt{1-v^2/c^2}} & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
X^0\\X^1\\X^2\\X^3
\end{pmatrix}
\end{equation}
$$
</div>

## The Field Tensor
The electric and magnetix field combine to form the field tensor $F_{\mu\nu}$ which contains every component of both the electric and magnetic field. This tensor can be used to represent the conditions of those fields at any point in space or time. It is antisymmetric, meaning that $F_{\mu\nu} = -F_{\nu\mu}$. The field tensor is defined in terms of the vector potential as follows:

<div class="equation">
$$
\begin{equation}
F_{\mu\nu} = \frac{\partial A_\nu}{\partial X^\mu} - \frac{\partial A_\mu}{\partial X^\nu}
\end{equation}
$$
</div>

Or in covariant vector form (downstairs indices):

<div class="equation">
$$
\begin{equation}
F_{\mu\nu} =
\begin{pmatrix}
0 & -E_x & -E_y & -E_z \\
E_x & 0 & B_z & -B_y \\
E_y & -B_z & 0 & B_x \\
E_z & B_y & -B_x & 0 \\
\end{pmatrix}
\end{equation}
$$
</div>

Or in its contravariant form (upstairs indices):

<div class="equation">
$$
\begin{equation}
F^{\mu\nu} =
\begin{pmatrix}
0 & E_x & E_y & E_z \\
-E_x & 0 & B_z & -B_y \\
-E_y & -B_z & 0 & B_x \\
-E_z & B_y & -B_x & 0 \\
\end{pmatrix}
\end{equation}
$$
</div>

## Einstein's Thought Experiment
Imagine coordinate system with the $y$ axis pointing up, the $x$ axis pointing to the right and the $z$ axis pointing towards you. Now imagine a conductive wire parellel to the $y$ axis moving with a velocity $v$ along the $x$ axis in the presence of a stationary magnet that produces a uniform magnetic field with only one component, $B_z$. There are no other electric or magnetic fields present. What will happen to an electron inside the wire? It will feel a force caused by the magnetic field and given by the Lorentz force law:

<div class="equation">
$$
\begin{equation}
\vec{F} = e\left(\vec{E} + \vec{v} \times \vec{B}\right)
\end{equation}
$$
</div>

Since there is no electric field present, the electron will feel a force that is both perpendicular to its velocity and the magnetic field. In this case, the electron will feel a force upwards (however, it will move downwards because of its negative charge convention).

Now consider the same situation but viewed from the rest frame of the electron. In this situation, the electron is stationary and the magnet (and thus the magnetic field) is moving with a velocity $v$ to the left along the $x$ axis. The force exerted on the electron must remain the same, but in the electron's frame it cannot be caused by a magnetic field, since the electron has no velocity. Therefore, the force on the electron must be due to an electric field. What Einstein learned from this simple and elegant thought experiment is that the field of a moving magnet must contain an electric component.
The force on the electron that is produced by the moving magnet is called the _electromotive force (EMF force)_. In this case, the moving magnet produces a downward electric field component $E_y$ that exerts an upward force on the electron (the force is opposite the field because the electron carries a negative charge). The EMF force is essentially the same as an electric field and it is a direct consequence of transforming the field tensor using the Lorentz tensor.

## Lorentz Transformation of the Field Tensor
Using the Lorentz tensor, we can transform our field tensor and find the electric field component in the $y$ direction in the rest frame of reference of the electron. The field tensor is transformed using the following equation:

<div class="equation">
$$
\begin{equation}\label{eq:lorentz_transform_of_field_tensor}
\left(F^\prime\right)^{\mu\nu} = L^\mu_{\,\,\sigma} L^\nu_{\,\,\tau} F^{\sigma\tau}
\end{equation}
$$
</div>

If we recall our initial setup, there was only a magnetic field present which only had a component $B_z$ in the $z$ direction. Therefore, the field tensor has only one nonzero component[^2]: $F^{12}$.
Let's compute the $y$ component of the electric field in the frame of the electron, or the 'primed' frame.

<div class="equation">
$$
\begin{equation}
\left(E^\prime\right)^y = \left(F^\prime\right)^{02}
\end{equation}
$$
</div>

Using equation \ref{eq:lorentz_transform_of_field_tensor}, we can find the component in the primed frame

<div class="equation">
$$
\begin{equation}
\left(E^\prime\right)^y = \left(F^\prime\right)^{02} = L^0_{\,\,1} L^2_{\,\,2} F^{12}
\end{equation}
$$
</div>

By looking at equation \ref{eq:lorentz_matrix}, we can substitute the elements of the field tensor, namely

$$L^0_{\,\,1} = \frac{-v}{\sqrt{1-v^2/c^2}}$$

and

$$L^2_{\,\,2} = 1$$

Therefore we can now write

<div class="equation">
$$
\begin{equation}
\left(E^\prime\right)^y = \left(F^\prime\right)^{02} = \frac{-vF^{12}}{\sqrt{1-v^2/c^2}}
\end{equation}
$$
</div>

But because $F^{12} = B^z$, we are left with

<div class="equation">
$$
\begin{equation}
\left(E^\prime\right)^y = \frac{-vB^z}{\sqrt{1-v^2/c^2}}
\end{equation}
$$
</div>

From this equation we can deduce, just like Einstein did, that a magnetic field, when viewed from a moving frame, will have an electric field component.

## References
Susskind, L., & Friedman, A. (2018). Special Relativity and Classical Field Theory: The Theoretical Minimum. Penguin Books, Limited.

***

[^1]: We can leave out the summation symbols because of the Einstein sum convention.
[^2]: Actually, it has two, if you count the antisymmetric component $F^{21} = -F^{12}$