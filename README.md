# Discrete-Time Quantum Walks

## Douglas&Wang, Fujiwara schemes (Toffoli-based)

* Reference by [Douglas & Wang](https://arxiv.org/abs/0706.0304),
* Reference by [Fujiwara](https://journals.aps.org/pra/abstract/10.1103/PhysRevA.72.032329).


Number of qubits _n_, number of steps _t_ and coin operator _C_ can be chosen.

_q0_ is the coin operator, qubits _[1, n-1]_ are used for encoding the nodes in the line.

The multi-controlled Toffoli gate _mct_ integrated in Qiskit is used, needing _O(n)_ auxiliary qubits, and using _O(n)_ basic gates. Since a step of the QW needs _O(n)_ such operations, the use of gates grows as _O(n^2)_.

<p align="center">
  <img src="https://raw.githubusercontent.com/VicPinaCanelles/discrete-time-quantum-walks/master/Fujiwara/qw-gate-fujiwara.png"><br>
  <i>Total gate count of one QW step vs. number of qubits (coin + nodes).</i>
</p>

Other implementations of the _mct_ gate use _O(n^2)_ gates without auxiliary qubits, making the total gate count grow as _O(n^3)_.


## Shakeel scheme (QFT-based)

* Reference by [Shakeel](https://arxiv.org/abs/1912.00978),
* Code by [Shakeel](https://github.com/asif-shakeel/QIS/blob/master/notebooks/discrete_time_quantum_walk_scalable.ipynb).

Total gate count grows as _O(n^2)_ with no need of auxiliary qubits.
