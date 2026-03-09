# KarlsruheMIS — Graph Independence Problems at Scale

We develop scalable algorithms for **independence problems on graphs**: Maximum Independent Set (MIS), Maximum Weight Independent Set (MWIS), 2-Packing Set, and Vertex Cover.

---

## The Problems

An **independent set** of a graph is a set of vertices with no two vertices adjacent. The **Maximum Independent Set (MIS)** problem asks for the largest such set; the **Maximum Weight Independent Set (MWIS)** problem generalizes this by assigning weights to vertices and maximizing total weight.

A **2-packing set** strengthens the independence condition: no two vertices in the set may share a common neighbor (i.e., they must be at distance at least 3). Finding a maximum 2-packing set is NP-hard and closely related to MIS — our solvers reduce it to an equivalent independent set instance after applying specialized data reduction rules.

The closely related **Vertex Cover** problem asks for the smallest set of vertices that touches every edge — its complement is a maximum independent set.

All these problems are NP-hard and among the hardest in practice. Large sparse graphs with millions of vertices, as they arise in network analysis, computational biology, and route planning, make exact and near-exact solutions especially challenging.

A key ingredient across all our solvers is **data reduction**: polynomial-time rules that shrink the input graph while preserving the optimal solution. Our [DataReductions](https://github.com/KarlsruheMIS/DataReductions) framework provides a comprehensive reference implementation of all known exact reduction rules for MWIS — usable as a standalone tool or as a library to integrate into your own solver.

**Applications** include map labeling, computer vision, combinatorial auctions, coding theory, molecular docking, facility location, and any setting that reduces to finding a maximum conflict-free selection.

---

## Projects

| Repository | Description |
|:-----------|:------------|
| [KaMIS](https://github.com/KarlsruheMIS/KaMIS) | Flagship framework: branch-and-reduce, evolutionary, and local search solvers for MIS and MWIS |
| [LearnAndReduce](https://github.com/KarlsruheMIS/LearnAndReduce) | GNN-guided reduction preprocessing for MWIS |
| [CHILS](https://github.com/KarlsruheMIS/CHILS) | Concurrent local search heuristic for MWIS |
| [DataReductions](https://github.com/KarlsruheMIS/DataReductions) | Reference implementation of data reduction rules for MWIS |
| [HyperMIS](https://github.com/KarlsruheMIS/HyperMIS) | Maximum independent sets on hypergraphs |
| [red2pack](https://github.com/KarlsruheMIS/red2pack) | Scalable solver for the 2-packing set problem |
| [pace-2019](https://github.com/KarlsruheMIS/pace-2019) | Winning solver of the PACE 2019 Challenge (vertex cover track) |

---

## Quick Start

### KaMIS
```bash
brew install KarlsruheMIS/kamis/kamis
redumis network.graph --output independent_set.txt --time_limit 60 --console_log
```

### CHILS
```bash
git clone https://github.com/KarlsruheMIS/CHILS.git && cd CHILS && make
./CHILS -g network.graph -p 16 -t 60 -o solution.txt
```

### LearnAndReduce
```bash
git clone https://github.com/KarlsruheMIS/LearnAndReduce.git && cd LearnAndReduce
./get_dep.sh && ./compile_all.sh
./deploy/reduce_and_chils network.graph --output=solution.txt --time_limit=60
```

### DataReductions
```bash
git clone https://github.com/KarlsruheMIS/DataReductions.git && cd DataReductions && make
./mwis_reduce -g network.graph --degree_one --domination --twin -v
```

### red2pack
```bash
git clone --recursive https://github.com/KarlsruheMIS/red2pack.git && cd red2pack
./compile_with_cmake.sh Release
./deploy/red2pack_branch_and_reduce network.graph --output=packing.txt --time_limit=60
```

---

## Papers

- S. Lamm, P. Sanders, C. Schulz, D. Strash, R. F. Werneck. **Finding Near-Optimal Independent Sets at Scale.** ALENEX 2016. [(PDF)](https://doi.org/10.1137/1.9781611974317.12)
- D. Hespe, C. Schulz, D. Strash. **Scalable Kernelization for Maximum Independent Sets.** ALENEX 2018. [(PDF)](https://doi.org/10.1137/1.9781611975055.16)
- S. Lamm, C. Schulz, D. Strash, R. Williger, H. Zhang. **Exactly Solving the Maximum Weight Independent Set Problem on Large Real-World Graphs.** ALENEX 2019. [(PDF)](https://doi.org/10.1137/1.9781611975499.11)
- D. Hespe, S. Lamm, C. Schulz, D. Strash. **WeGotYouCovered: The Winning Solver from the PACE 2019 Challenge.** CSC 2020. [(PDF)](https://doi.org/10.1137/1.9781611976229.1)
- S. Lamm, P. Sanders, C. Schulz. **Graph Partitioning for Independent Sets.** SEA 2015. [(PDF)](https://doi.org/10.1007/978-3-319-20086-6_6)

A full list of references is available in the [KaMIS documentation](https://karlsruhemis.github.io).

---

## Contact

**Heidelberg University, Institute of Computer Science**
https://karlsruhemis.github.io
