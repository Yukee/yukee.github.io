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
	\lim_{t \to \infty} \langle \hat{O} \rangle(t) = \text{tr}(\hat{\rho}^\text{Boltzmann}(\beta)\hat{O}).
\\]


* The quantum system is isolated but somehow acts as its own bath and thermalizes by itself. This could happen is our system is very large: then for a (small) part of the system it can be as if the (huge) remaining part was an effective bath. 
It is this latter case we are interested in.

# The paradox of irreversibility
We consider from now on the second scenario.
In this scenario, the expectation value of macroscopic observables thermalizes.
The simplest explanation for this observation is that the density matrix itself thermalizes:
\\[
	\lim_{t \to \infty} \hat{\rho}(t) = \hat{\rho}^\text{Boltzmann}(\beta).
\\]
In this case, memory of the initial state is lost in the large time limit.
However, since the quantum system is isolated, its density matrix evolves unitarily:
\\[
	\rho(t) = e^{-i H t} \rho(0) e^{i H t}.
\\]
This evolution is *reversible*: the memory of the initial state of the system is never lost.
Therefore, is it impossible for the reduced density matrix to thermalize.
This is the paradox of irreversibility.

The paradox is only apparent. When we say that a quantum system thermalizes, we mean that its physical, macroscopic observables obey Boltzmann laws. 
So, we do not need the density matrix to converge to Boltzmann, but to act on physical observables *as if* it had thermalized:
\\[
	\lim_{t \to \infty} \langle \hat{O} \rangle(t) = \text{tr}(\hat{\rho}^\text{Boltzmann}(\beta) \hat{O}).
\\]
This requirement constrains the eigenstates of the system, as we see now.

## The diagonal ensemble

If the system is initatially prepared in a pure state \\( |\psi_0\rangle = \sum_n c_n |n\rangle \\), then
\\[
	\lim_{t \to \infty} \langle \hat{O} \rangle(t) = \sum_n |c_n|^2 O_{n,n}.
\\]
Since by asumption the system is thermal, the \\(c_n\\) coefficients of the eigendecomposition verify
\\[
	\sum_n |c_n|^2 O_{n,n} = \text{tr}(\rho^\text{Boltzmann}(\beta)O).
\\]
It is as if the coefficients of the eigendecomposition were drawn from a statistical ensemble, which we shall call the *diagonal ensemble*.

## The microcanonical ensemble

Moreover, since our system is closed, and since we suppose it is thermal, the expectation value of macroscopic observables are drawn from a microcanonical ensemble:
\\[
	\langle O \rangle(t \to \infty) = \text{tr}(\rho^\text{Boltzmann}(\beta)O) = \langle O \rangle^\text{micro}(E),
\\]
where $$E = \langle H \rangle$$ is the energy of the system at inverse temperature $$\beta$$.
Explicitly, the microcanonical average writes
\\[
	\langle O \rangle^\text{micro}(E) = \frac{1}{\Omega([E,E+dE))} \sum_{n|E_n \in [E,E+dE)} O_{n,n}.
\\]

# The eigenstate thermalization hypothesis
Can we reunite the microcanonical and diagonal ensembles in a single global picture? If the eigenstate thermalization hypothesis holds, the answer is yes!
Under the eigenstate thermalization hypothesis, *eigenstates themselves act as thermal states*.

Let us prepare our system initially in the (eigen)state $$|n\rangle$$.
Then, according to the ETH,
\\[
	O_{n,n} = \langle O \rangle^\text{micro}(E_n).
\\]
<!---
Reciprocally, assuming that $$O_{n,n}$$ verifies the above formula, we recover immediately that the system is thermal.
Therefore, the ETH is equivalent to the above formula.
--->

It is easy to check that this formula is compatible with both the microcanonical and the diagonal ensembles, therefore uniting them.
The ETH is a nice hypothesis, but does it hold as soon as the quantum system is thermal?
There is no thermal closed quantum system for which the ETH could not be validated.
Thus, so far, the answer seems to be yes...

## Temperature of a given eigenstate
In this part we examine a technical point: how to define the temperature of an eigenstate.
Let us consider a particle-hole symmetric system. Then if energy $$E$$ is in the spectrum, energy $$-E$$ is in the spectrum as well.
Let $$-E_1 < -E_2 < \dots < E_2 < E_1$$ <!--- >>>>> ---> be the ordered set of energies of the system. 
Because the system is thermal, we have
\\[
	\langle H \rangle = \frac{1}{Z(\beta)} \text{tr}(H e^{-\beta H}).
\\]
Using the particle-hole symmetry,
\\[
	\langle H \rangle = -\frac{\sum_{n} E_n \sinh(\beta E_n)}{\sum_n \cosh(\beta E_n)}.
\\]
From this equation, we can determine the temperature of any eigenstate. 
For the groundstate, the equation becomes
\\[
	E_1 = \frac{\sum_{n} E_n \sinh(\beta E_n)}{\sum_n \cosh(\beta E_n)},
\\]
whose solution is $$\beta = \infty$$: *the groundstate has zero temperature*.
Notice that if $$\beta_n$$ is the temperature of the eigenstate $$-E_n$$, then $$-\beta_n$$ is the temperature of its particle-hole symmetric partner $$E_n$$.
In particular, *the state at $$E=0$$ (if it exists) has infinite temperature*.
In between the two the temperature varies smoothly and monotonously.
Therefore, as we increase the energy we explore regions of higher and higher temperature.

# The many-body localized (MBL) phase

There are however closed quantum systems for which the ETH does not hold: systems which are not thermal at all. 
These we call many-body localized, or MBL systems.


<!---
References
--->
[nandkishore_huse]: https://arxiv.org/abs/1404.0686
