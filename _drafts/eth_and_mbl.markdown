---
layout: post
title:  "Thermodynamics of a quantum system"
date:   2017-08-04 16:08:00 +0200
categories: quantum physics, many-body
---

# Two scenarios for thermalization of a quantum system
In this part we follow [a review by Nandkishore and Huse][nandkishore_huse], and a review by Alet and Laflorencie (not online yet).
We want to discuss possible ways a quantum system thermalizes. So, first, let us define what me mean by ''thermal''. We say that a quantum system is thermal if the expectation value of any physical observable is given by a Boltzmann law. 
In general, quantum mechanics tells us that the expectation value of an observable writes
\\[
	\langle \hat{O} \rangle = \text{tr}(\hat{\rho}(t) \hat{O}),
\\]
where \\(\hat{\rho}(t)\\) is the density matrix of the system at time \\(t\\).
Our system is thermal if and only if
\\[
	\langle \hat{O} \rangle(t) = \text{tr}(\hat{\rho}(t)\hat{O}) = \text{tr}(\hat{\rho}^\text{Boltzmann}(\beta)\hat{O}),
\\]
where \\(\hat{H}\\) is the Hamiltonian of our quantum system, and \\( \\) the Boltzmann density matrix at inverse temperature \\(\beta\\):
\\[
	\hat{\rho}^\text{Boltzmann}(\beta) = \frac{e^{-\beta \hat{H}}}{Z(\beta)}.
\\]

There are two ways we can imagine a quantum system thermalizes.
* Thermalization is ''given'' by an external *classical* bath to which our quantum system is coupled.
Then any observable \\(\hat{O}(t)\\), after some time, thermalizes to the temperature of the bath, i.e.
\\[
	\lim_{t \to \infty} \hat{\rho}(t) = \hat{\rho}^\text{Boltzmann}(\beta).
\\]

* The quantum system is isolated but somehow acts as its own bath and thermalizes by itself. This could happen is our system is very large: then for a (small) part of the system it can be as if the (huge) remaining part was an effective bath. 
It is this latter case we are interested in.

# The paradox of irreversibility and the eigenstate thermalization hypothesis
In the second scenario (which we study in this post), the quantum system is isolated, so its density matrix simply evolves unitarily:
\\[
	\rho(t) = e^{-i H t} \rho(0) e^{i H t}.
\\]
This evolution is *reversible*: the memory of the initial state of the system is never lost.
Therefore, is it impossible for the reduced density matrix to thermalize (i.e. to tend to a Boltzmann distribution).
However, there are cases were an isolated quantum system thermalizes. This is the paradox of irreversibility.

The paradox is only apparent. When we say that a quantum system thermalizes, we mean that its physical, macroscopic observables obey Boltzmann laws. 
So, we do not need the density matrix to converge to Boltzmann, but to act on physical observables *as if* it had converged to Boltzmann:
\\[
	\lim_{t \to \infty} \langle \hat{O} \rangle(t) = \text{tr}(\hat{\rho}^\text{Boltzmann}(\beta)\hat{O}).
\\]

## The diagonal ensemble

If the system is initatially prepared in a pure state \\( \ket{\psi_0} = \sum_n c_n \ket{n} \\), then
\\[
	\lim_{t \to \infty} \langle \hat{O} \rangle(t) = \sum_n |c_n|^2 O_{n,n}.
\\]
For the thermalization to hold, the \\(c_n\\) coefficients of the eigendecomposition must act as random variable drawn from a Boltzmann distribution depending on an effective inverse temperature \\(\beta(\psi_0)\\).

## The microcanonical ensemble

Since our system is close, and since we suppose it is thermal, we may expect the expectation value of macroscopic observables to be drawn from a microcanonical ensemble:
\\[
	\langle O \rangle(t \to \infty) = \langle O \rangle^\text{micro}
\\]
with 
\\[
	\langle O \rangle^\text{micro} = \frac{1}{\Omega([E,E+dE))} \sum_{n|E_n \in [E,E+dE)} O_{n,n}.
\\]

## The eigenstate thermalization hypothesis
Under the eigenstate thermalization hypothesis, eigenstates themselves act as thermal states:
\\[
	O_{n,n} = \langle O \rangle^\text{micro}.
\\]


<!---
References
--->
[nandkishore_huse]: https://arxiv.org/abs/1404.0686
