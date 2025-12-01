In our experiments, we utilized three classic heterogeneous graph datasets: Chameleon, Squirrel, and Roman-empire. Notably, for the Chameleon and Squirrel datasets, we employed the recently released filtered versions[^1] in which duplicate nodes have been removed. The selected baselines include three representative heterogeneous GNNs—H2GCN, GPRGNN, and ACMGCN—as well as three GNNs utilizing mixed aggregation functions: PNA, AAGCN, and PieCoN. 

Experimental results indicate that while the original MoMP exhibits suboptimal performance on heterogeneous datasets, it nonetheless outperforms standard GCN and GAT models. **We introduced a variant termed MoMP (neighbor split), which incorporates an enhancement strategy analogous to H2GCN.** This method separates ego-features from neighbor-features during message passing and randomly samples ten second-order neighbors for each node. Consequently, the message formulation is optimized from $h_j, j \in \mathcal{N}_i$ to $[h_i \parallel \sum(h_j)], j \in \mathcal{N}_i \cup \mathcal{N}^2_i$. **The results demonstrate that implementing this simple modification yields substantial performance gains across all datasets, achieving state-of-the-art performance on the Chameleon dataset. This not only demonstrates MoMP’s strong compatibility with message optimization strategies employed in heterogeneous GNNs, but also highlights its significant potential on heterogeneous graph datasets.**

The main results is shown in "Extra Experiments.png".



[^1]:Platonov O, Kuznedelev D, Diskin M, et al. A critical look at the evaluation of GNNs under heterophily: Are we really making progress?[J]. arXiv preprint arXiv:2302.11640, 2023.
Rey S, Navarro M, Tenorio V M, et al. Redesigning graph filter-based GNNs to relax the homophily assumption[C]//ICASSP 2025-2025 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP). IEEE, 2025: 1-5.
