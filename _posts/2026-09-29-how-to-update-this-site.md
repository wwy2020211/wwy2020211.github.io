---
layout: post
title: TA in PhD life
description: My own TA experience in my PhD work
tags: [meta]
lang: en
---

**2026-2027 Winter semester**

**Quantum Mechanism For Engineer**
1. Understanding the Hamiltonian through Input–Output Systems
If you have studied transfer functions, transmission lines, or state-space models, you already have a useful intuition for understanding Hamiltonian matrix elements. We first identify the input and output channels of a linear system, then connect the matrix to quantum dynamics.
A two-input, two-output system
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 230" role="img" aria-label="Two input ports I1 and I2 connect to a transfer matrix T, which connects to output ports O1 and O2" style="max-width:640px;width:100%;height:auto;display:block;margin:1rem auto;color:currentColor">
  <g stroke="currentColor" fill="none" stroke-width="2">
    <rect x="225" y="36" width="190" height="158" rx="3"/>
    <line x1="76" y1="79" x2="225" y2="79"/>
    <line x1="76" y1="155" x2="225" y2="155"/>
    <line x1="415" y1="79" x2="564" y2="79"/>
    <line x1="415" y1="155" x2="564" y2="155"/>
    <path d="M215 73 L225 79 L215 85 M215 149 L225 155 L215 161 M554 73 L564 79 L554 85 M554 149 L564 155 L554 161"/>
  </g>
  <g fill="currentColor" font-family="Arial, sans-serif" font-size="20" text-anchor="middle">
    <text x="46" y="85">I₁</text><text x="46" y="161">I₂</text>
    <text x="596" y="85">O₁</text><text x="596" y="161">O₂</text>
    <text x="320" y="104">Transfer matrix</text><text x="320" y="139" font-size="30">T</text>
  </g>
</svg>

The relation between the input and output amplitudes is
<div class="math-display">\[
\begin{pmatrix}O_1\\O_2\end{pmatrix}
=\underbrace{\begin{pmatrix}T_{11}&T_{12}\\T_{21}&T_{22}\end{pmatrix}}_{T}
\begin{pmatrix}I_1\\I_2\end{pmatrix}.
\]</div>

In this convention, columns label input channels and rows label output channels:
<div class="math-display">\[
O_1=T_{11}I_1+T_{12}I_2,\qquad O_2=T_{21}I_1+T_{22}I_2.
\]</div>

Thus, <span class="math-inline">\(T_{12}\)</span> is the contribution from input 2 to output 1, per unit input 2 with the other input set to zero. If <span class="math-inline">\((I_1,I_2)=(0,1)\)</span>, then <span class="math-inline">\((O_1,O_2)=(T_{12},T_{22})\)</span>.
From a matrix mapping to quantum dynamics
A Hamiltonian is also a linear operator, but it is not itself a transmission coefficient or a measurement probability. It determines the time derivative of the quantum state through Schrödinger's equation:
<div class="math-display">\[
i\hbar\frac{d}{dt}|\psi(t)\rangle=H|\psi(t)\rangle.
\]</div>

In a two-state orthonormal basis, <span class="math-inline">\(|\psi\rangle=c_1|1\rangle+c_2|2\rangle\)</span>, so
<div class="math-display">\[
i\hbar\begin{pmatrix}\dot c_1\\\dot c_2\end{pmatrix}
 =\begin{pmatrix}H_{11}&H_{12}\\H_{21}&H_{22}\end{pmatrix}
 \begin{pmatrix}c_1\\c_2\end{pmatrix}.
\]</div>

Therefore,
<div class="math-display">\[
i\hbar\dot c_1=H_{11}c_1+H_{12}c_2,\qquad
 i\hbar\dot c_2=H_{21}c_1+H_{22}c_2.
\]</div>

The diagonal terms <span class="math-inline">\(H_{11}\)</span> and <span class="math-inline">\(H_{22}\)</span> contribute to each basis component's evolution; in the absence of coupling they set its phase rotation rate. The off-diagonal terms <span class="math-inline">\(H_{12}\)</span> and <span class="math-inline">\(H_{21}\)</span> couple the two components, so an amplitude in state 2 can affect the rate of change of amplitude in state 1, and vice versa. For a closed system, <span class="math-inline">\(H=H^\dagger\)</span>, hence <span class="math-inline">\(H_{21}=H_{12}^*\)</span>.
Why <span class="math-inline">\(H_{12}=\langle1|H|2\rangle\)</span>: a geometric picture
Apply <span class="math-inline">\(H\)</span> to the second unit basis vector <span class="math-inline">\(|2\rangle\)</span>. Let <span class="math-inline">\(|2'\rangle:=H|2\rangle\)</span>. Then the coefficient of the output along <span class="math-inline">\(|1\rangle\)</span> is obtained by projecting onto <span class="math-inline">\(\langle1|\)</span>:
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 290" role="img" aria-label="Orthogonal basis vectors 1 and 2, transformed vector 2 prime, and its projection along basis 1" style="max-width:640px;width:100%;height:auto;display:block;margin:1rem auto;color:currentColor">
  <defs><marker id="qmArrow" markerWidth="7" markerHeight="7" refX="6" refY="3.5" orient="auto"><path d="M0 0 L7 3.5 L0 7 Z" fill="currentColor"/></marker></defs>
  <g stroke="currentColor" fill="none" stroke-width="2" marker-end="url(#qmArrow)">
    <line x1="100" y1="240" x2="545" y2="240"/><line x1="100" y1="240" x2="100" y2="24"/>
    <line x1="100" y1="240" x2="350" y2="62" stroke-width="3"/>
    <line x1="100" y1="240" x2="350" y2="240" stroke-width="3"/>
  </g>
  <line x1="350" y1="62" x2="350" y2="240" stroke="currentColor" stroke-width="1.5" stroke-dasharray="6 5"/>
  <g fill="currentColor" font-family="Arial,sans-serif" font-size="19">
    <text x="550" y="246">|1⟩</text><text x="60" y="25">|2⟩</text>
    <text x="360" y="56">|2′⟩ = H|2⟩</text>
    <text x="215" y="264">H₁₂ |1⟩</text>
    <text x="111" y="275" font-size="14">0</text>
  </g>
</svg>

<div class="math-display">\[
H|2\rangle=H_{12}|1\rangle+H_{22}|2\rangle
\quad\Rightarrow\quad
\boxed{\langle1|H|2\rangle=H_{12}}.
\]</div>

Read the expression from right to left: state 2 is the input; <span class="math-inline">\(H\)</span> acts on it; <span class="math-inline">\(\langle1|\)</span> extracts the component along output direction 1. The diagram illustrates real components; for general complex amplitudes, the inner product gives a complex coefficient rather than a geometric length.
Takeaway: the input–output analogy explains the meaning and ordering of matrix indices; Schrödinger's equation tells us how the Hamiltonian translates those couplings into quantum-state dynamics.
