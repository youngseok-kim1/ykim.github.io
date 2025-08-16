---
layout: page
title: Research
permalink: /research/
---

## Overview

Benchmarking is essential for evaluating quantum device performance and guiding future improvements. As quantum circuits grow in complexity, multiple noise sources often contribute comparably to overall errors, making it increasingly difficult to identify the dominant performance bottlenecks. Carefully designed benchmarking frameworks are therefore critical for isolating these error sources and informing targeted optimization strategies. <br>

**Device level benchmarks** focus on subsystem metrics such as gate fidelity, crosstalk, and measurement errors. While they are effective in identifying general non-idealities, they often lack direct relevance to real-world applications. **Holistic benchmarks** like Quantum Volume evaluate performance on representative quantum tasks. These benchmarks provide application-level insights but can be unpredictable when applied to other algorithms and often obscure the specific sources of failure. <br>

Our group aims to bridge the gap between device-level and holistic benchmarking by establishing a framework that connects individual error sources to algorithm-level performance impact. Namely, we first have a concrete hardware platform and representative holistic benchmark helps us to identify non-ideality that matters for the target algorithm. Isolating and investigating detailed mechanism via device level study allow us to have a comprehensive view on what to solve first and how we improve it. This framework is essential for the co-optimization of physical qubit architectures and quantum algorithm design. <br>

## Quantum error mitigation (QEM)

Typical QEM consists of three steps: characterize noise, manipulate noise, and post-process the results. Within the QEM framework, noise outside stochastic gate error makes both noise characterization and manipulation steps challenging. 

**Coherent error** is one example whose nature is far from stochastic, especially with a structured circuit such as the one used in quantum simulation. We utilized quantum circuit for spin dynamics as a holistic benchmark and provided that dynamical decoupling and Pauli twirling helps to address underlying coherent noise [1], now adopted as a common practice for running large scale quantum circuit [2]. 

**Qubit stability** is another example that introduces another non-ideality. One of the well-known source of superconducting qubit fluctuation is qubit-two level system (TLS) interaction. We identified that qubit-TLS interaction is one of the critical noise sources from the holistic benchmark [3,4]. We implement a hardware solution that modulates the qubit-TLS environment and established optimization strategies to stabilize the qubit [4]. This hardware-driven improvement has been further verified by holistic benchmark, showing clear improvement in QEM experiments. <br>

QEM depends on **precise control of noise strength**. Traditionally, noise scaling was achieved by varying control pulse duration to adjust qubit-bath interaction time. However, noise mechanisms are complex and do not scale linearly with time, making large-scale noise scaling challenging. Collaborating with algorithm researchers, we developed methods to learn device noise [5] and manipulate it by stochastically inserting single-qubit Pauli gates. This approach enabled quantum simulation using 127 qubits—beyond the brute-force classical regime—demonstrating the utility of noisy quantum computers [3]. <br>

Our effort to scale QEM demonstrates that we must understand non-idealities arising from a concrete hardware platform and how they limit the performance of the target algorithm. We aims to have a benchmarking framework that will inform us on existing non-idealities that matters for QEM algorithm and helps us to devise solutions through optimization on circuit composition, gate calibration routine, algorithm, and hardware. 

[1] Kim, Youngseok, Christopher J. Wood, Theodore J. Yoder, Seth T. Merkel, Jay M. Gambetta, Kristan Temme, and Abhinav Kandala. "Scalable error mitigation for noisy quantum circuits produces competitive expectation values." Nature Physics 19, no. 5 (2023): 752-759. <br>
[2] Matthias Steffen, [What’s the difference between er-
ror suppression, error mitigation, and error cor-
rection?](https://www.ibm.com/quantum/blog/quantum-error-suppression-mitigation-correction) <br>
[3] Kim, Youngseok, Andrew Eddins, Sajant Anand, Ken Xuan Wei, Ewout Van Den Berg, Sami Rosenblatt, Hasan Nayfeh et al. "Evidence for the utility of quantum computing before fault tolerance." Nature 618, no. 7965 (2023): 500-505. <br>
[4] Kim, Youngseok, Luke CG Govia, Andrew Dane, Ewout van den Berg, David M. Zajac, Bradley Mitchell, Yinyu Liu et al. "Error mitigation with stabilized noise in superconducting quantum processors." arXiv preprint arXiv:2407.02467 (2024) (accepted at Nature Communications) <br>
[5] E. van den Berg, Z. K. Minev, A. Kandala, and K. Temme, Nature Physics (2023), ISSN 1745-2481 <br>

## Quantum error correction (QEC)

There is growing interest in making quantum error correction (QEC) codes practical. Most efforts focus on code types and architectures, but these must be complemented by a realistic understanding of hardware noise. Evaluating QEC performance on real hardware is inherently complex due to the interplay of code structure, noise during syndrome measurement, and decoder algorithms. As a result, QEC metrics are often convoluted, making it difficult to attribute errors to specific components.

Our group seeks to clarify the connection between device-level behavior and algorithmic performance in QEC. For example, we studied the heavy-hex code at small scale and identified non-local noise induced by readout operations [1], which we mitigated using carefully scheduled dynamical decoupling. We also investigated leakage errors caused by gate operations and mid-circuit measurements, which limit the number of QEC cycles that can be executed reliably [2].

[1] Chen, Edward H., Theodore J. Yoder, Youngseok Kim, Neereja Sundaresan, Srikanth Srinivasan, Muyuan Li, Antonio D. Córcoles, Andrew W. Cross, and Maika Takita. "Calibrated decoders for experimental quantum error correction." Physical Review Letters 128, no. 11 (2022): 110504 <br>
[2] Sundaresan, Neereja, Theodore J. Yoder, Youngseok Kim, Muyuan Li, Edward H. Chen, Grace Harper, Ted Thorbeck, Andrew W. Cross, Antonio D. Córcoles, and Maika Takita. "Demonstrating multi-round subsystem quantum error correction using matching and maximum likelihood decoders." Nature Communications 14, no. 1 (2023): 2852. <br>


