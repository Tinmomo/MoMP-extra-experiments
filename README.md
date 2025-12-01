In our experiments, we utilized three classic heterogeneous graph datasets: Chameleon, Squirrel, and Roman-empire. Notably, for the Chameleon and Squirrel datasets, we employed the recently released filtered versions[^1] in which duplicate nodes have been removed. The selected baselines include three representative heterogeneous GNNs—H2GCN[^2], GPRGNN[^3], and ACMGCN[^4]—as well as three GNNs utilizing mixed aggregation functions: PNA[^5], AAGCN[^6], and PieCoN[^7]. 

Experimental results indicate that while the original MoMP exhibits suboptimal performance on heterogeneous datasets, it nonetheless outperforms standard GCN and GAT models. **We introduced a variant termed MoMP (neighbor split), which incorporates an enhancement strategy analogous to H2GCN.** This method separates ego-features from neighbor-features during message passing and randomly samples ten second-order neighbors for each node. Consequently, the message formulation is optimized from $h_j, j \in \mathcal{N}_i$ to $[h_i \parallel \sum(h_j)], j \in \mathcal{N}_i \cup \mathcal{N}^2_i$. **The results demonstrate that implementing this simple modification yields substantial performance gains across all datasets, achieving state-of-the-art performance on the Chameleon dataset. This not only demonstrates MoMP’s strong compatibility with message optimization strategies employed in heterogeneous GNNs, but also highlights its significant potential on heterogeneous graph datasets.**

The main results is shown in "Extra Experiments.png".



[^1]:Platonov O, Kuznedelev D, Diskin M, et al. A critical look at the evaluation of GNNs under heterophily: Are we really making progress?[J]. arXiv preprint arXiv:2302.11640, 2023.

[^2]:Zhu J, Yan Y, Zhao L, et al. Beyond homophily in graph neural networks: Current limitations and effective designs[J]. Advances in neural information processing systems, 2020, 33: 7793-7804.

[^3]:Chien E, Peng J, Li P, et al. ADAPTIVE UNIVERSAL GENERALIZED PAGERANK GRAPH NEURAL NETWORK[C]//9th International Conference on Learning Representations, ICLR 2021. 2021.

[^4]:Luan S, Hua C, Lu Q, et al. Revisiting heterophily for graph neural networks[J]. Advances in neural information processing systems, 2022, 35: 1362-1375.

[^5]:Corso G, Cavalleri L, Beaini D, et al. Principal neighbourhood aggregation for graph nets[J]. Advances in neural information processing systems, 2020, 33: 13260-13271.

[^6]:Rey S, Navarro M, Tenorio V M, et al. Redesigning graph filter-based GNNs to relax the homophily assumption[C]//ICASSP 2025-2025 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP). IEEE, 2025: 1-5.

[^7]:Martirosyan V, Giraldo J H, Malliaros F D. Piecewise Constant Spectral Graph Neural Network. Transactions on Machine Learning Research, 2025.
